# $Id$
# Contributor: TheKit <nekit1000 at gmail.com>
# Contributor: Bart Ribbers <bribbers@disroot.org>
# Contributor: Alexey Andreyev <aa13q@ya.ru>
# Maintainer: James Kittsmiller (AJSlye) <james@nulogicsystems.com>

_host="github.com"
_project=nemomobile-ux
_basename=glacier-app
_branch=master

_gitname=lib${_basename//-/}
pkgname=qt5-$_basename-git

pkgver=0.5.0.r0.gfeb122a

pkgrel=1
pkgdesc="Glacier Application library"
arch=('x86_64' 'aarch64')
url="https://$_host/$_project/$_gitname#branch=$_branch"
license=('LGPL-2.0-or-later')
depends=('qt5-declarative' 'qt5-quickcontrols-nemo-git')
makedepends=('git')
provides=("${pkgname%-git}")
conflicts=("${pkgname%-git}")
source=("${pkgname}::git+${url}")
md5sums=('SKIP')

pkgver() {
    cd "${srcdir}/${pkgname}"
    git describe --long --tags | sed 's/\([^-]*-g\)/r\1/;s/-/./g'
}

build() {
    cd "${srcdir}/${pkgname}"
    qmake
    make
}

package() {
    cd "${srcdir}/${pkgname}"
    make INSTALL_ROOT="$pkgdir/" install
}
 
