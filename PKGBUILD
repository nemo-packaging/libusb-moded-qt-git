## $Id$
# Maintainer: TheKit <nekit1000 at gmail.com>
# Maintainer: James Kittsmiller (AJSlye) <james@nulogicsystems.com>

pkgname=libusb-moded-qt-git
pkgver=1.9.r0.g0544b73
pkgrel=1
pkgdesc="A library of Qt5 bindings for usb_moded"
arch=('x86_64' 'aarch64')
url="https://git.sailfishos.org/mer-core/libusb-moded-qt"
license=('GPL')
depends=('qt5-base' 'usb-moded')
makedepends=('git')
provides=("${pkgname%-git}")
conflicts=("${pkgname%-git}")
source=('git+https://git.sailfishos.org/mer-core/libusb-moded-qt.git')
md5sums=('SKIP')

pkgver() {
	cd "$srcdir/${pkgname%-git}"
	git describe --long --tags | sed 's/\([^-]*-g\)/r\1/;s/-/./g'
}

build() {
	cd "$srcdir/${pkgname%-git}"
	qmake
	make
}

package() {
	cd "$srcdir/${pkgname%-git}"
	make INSTALL_ROOT="$pkgdir/" install
}
