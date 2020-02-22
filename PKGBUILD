# $Id$
# Maintainer: TheKit <nekit1000 at gmail.com>
# Maintainer: James Kittsmiller (AJSlye) <james@nulogicsystems.com>

pkgname=libglacierapp-git
pkgver=0.4.0.r0.g3cf6a55
pkgrel=1
pkgdesc="Glacier Application library"
arch=('x86_64' 'aarch64')
url="https://github.com/nemomobile-ux/libglacierapp"
license=('GPL')
depends=('mlite' 'qt5-declarative')
makedepends=('git')
provides=("${pkgname%-git}")
conflicts=("${pkgname%-git}")
source=('git+https://github.com/nemomobile-ux/libglacierapp.git')
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
 
