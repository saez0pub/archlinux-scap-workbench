# Maintainer: Jean Prat https://github.com/saez0pub/archlinux-scap-security-guide
pkgname=scap-workbench
pkgver=1.2.0
pkgrel=1
pkgdesc="SCAP Scanner And Tailoring Graphical User Interface"
arch=('any')
url="http://www.open-scap.org/tools/scap-workbench"
license=('https://github.com/OpenSCAP/scap-workbench/blob/v1-1/COPYING')
depends=('openssh' 'util-linux' 'qt5-base' 'qt5-xmlpatterns' 'openscap')
makedepends=('cmake' 'qt5-base' 'qt5-xmlpatterns' 'openscap')
source=("https://github.com/OpenSCAP/scap-workbench/releases/download/${pkgver}/scap-workbench-${pkgver}.tar.bz2")
md5sums=('3c82874f02214f8a6960349ae48559a4')

build() {
	cd "$srcdir/${pkgname}-${pkgver}"
	mkdir -p build; cd build
        cmake ../
        make
}

package() {
	cd "$srcdir/${pkgname}-${pkgver}/build"
	make DESTDIR="$pkgdir/" install
        mv "$pkgdir/usr/local/share/man" "$pkgdir/usr/local/man"
}
