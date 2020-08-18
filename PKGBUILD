pkgname=sputnik-browser
pkgver=4.12539
pkgdesc="That one Russian chromium fork filled with spyware and ads"
pkgrel=1

arch=('x86_64')
license=('custom')
depends=('libxss' 'nspr' 'nss' 'gtk3'
         'libegl' 'libgles' 'gconf')
source=("http://browser-deb.sputnik.ru/ubuntu/pool/main/s/sputnik-browser-stable/sputnik-browser-stable_4.1.2539.0-1_amd64.deb")
md5sums=('90f67babf20ed5e1c599ebe5de77a6c1')

prepare() {
	tar -xf data.tar.xz
}

package() {
	srcdir=$(pwd)
	install -d "$pkgdir"/opt/$pkgname
	cp -a $srcdir/opt/sputnik-browser/. "$pkgdir"/opt/$pkgname
	install -d "$pkgdir"/usr/{bin,share/applications,share/pixmaps}
	cp $srcdir/opt/$pkgname/product_logo_128.png "$pkgdir"/usr/share/pixmaps/$pkgname.png
	ln -s $srcdir/opt/sputnik-browser/browser "$pkgdir"/usr/bin/sputnik-browser-stable
	cp $srcdir/usr/share/applications/$pkgname.desktop "$pkgdir"/usr/share/applications/
	}
