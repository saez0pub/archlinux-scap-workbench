# Maintainer: Jean Prat https://github.com/saez0pub/archlinux-scap-security-guide
pkgname=scap-workbench
pkgver=1.1.1
pkgrel=1
pkgdesc="SCAP Scanner And Tailoring Graphical User Interface"
arch=('any')
url="http://www.open-scap.org/tools/scap-workbench"
license=('https://github.com/OpenSCAP/scap-workbench/blob/v1-1/COPYING')
depends=('cmake' 'make' 'openssh')
makedepends=('make' 'git')
source=("https://github.com/OpenSCAP/scap-workbench/releases/download/${pkgver}/scap-workbench-${pkgver}.tar.bz2")
md5sums=('b13e410e5825b0762e5008f871b48f03')

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
