# Maintainer: ABHISHEK SHARMA
pkgname=mplaympv
github="plaympv"
pkgname=$plaympv
pkgver=0.8
pkgrel=1
pkgdesc='Qt5/QML based player for MatsyaOS.'
url="https://github.com/matsyaos/${github}"
conflicts=("${pkgname}")
provides=("${pkgname}")
arch=('i686' 'x86_64')
license=('GPL2')
makedepends=('git')
depends=('qt5-x11extras' 'qt5-quickcontrols' 'mpv')
sha256sums=('SKIP')
source=("https://github.com/matsyaos/plaympv")
pkgver() {
	cd "${srcdir}/${_pkgname}"
    printf '0.r%s.g%s' \
        "$(git rev-list --count master)" \
        "$(git log -1 --format='%h')"
}

prepare() {
    mkdir -p "${srcdir}/${_pkgname}/build"
}

build() {
	cd "${srcdir}/${_pkgname}/build"
    qmake ..
    make
}

package() {
	cd "${srcdir}/${_pkgname}/build"
    make INSTALL_ROOT="${pkgdir}/" install
}
