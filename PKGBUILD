# Maintainer: Agung Wijaya <hallo@yaya.my.id>

pkgname=qjackctl
pkgver=0.9.11
pkgrel=1
pkgdesc='QjackCtl - JACK Audio Connection Kit Qt GUI Interface'
arch=('amd64')
makedepends=('cmake' 'git' 'qttools5-dev' 'libqt5svg5-dev' 'libjack-jackd2-dev' 'portaudio19-dev')
provides=('qjackctl')
conflicts=('qjackctl')
license=('GPL2')
url='https://qjackctl.sourceforge.io/'

source=("${pkgname}"'::git+https://github.com/rncbc/qjackctl.git')
sha256sums=('SKIP')
noextract=()

prepare() {
    cd "${srcdir}/${pkgname}"
    printf "r%s.%s" "$(git rev-list HEAD --count --first-parent)" "$(git rev-parse --short HEAD)"
}

build() {
    cmake -B build \
    -DCMAKE_INSTALL_PREFIX=/usr \
    -DCMAKE_BUILD_TYPE=Release \
    -DCONFIG_QT6=OFF \
    -S "$srcdir/${pkgname}"
    cmake --build build
}

package() {
    DESTDIR="$pkgdir" cmake --install build
}

# vim: set sw=4 expandtab:
