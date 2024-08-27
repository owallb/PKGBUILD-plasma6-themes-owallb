# Maintainer: Oscar Wallberg <oscar.wallberg@pm.me>
# shellcheck disable=SC2034
_name=plasma6-themes-owallb
pkgname=${_name}-git
pkgver=0.1.r0.g37fdc8e
pkgrel=1
pkgdesc="Desktop theme for Plasma 6"
arch=(any)
url="https://github.com/owallb/${_name}"
license=('BSD-3-Clause')
makedepends=('git')
conflicts=("${_name}")
provides=("${_name}=${pkgver}")
source=("git+https://github.com/owallb/${_name}.git")
sha256sums=('SKIP')

pkgver() {
    cd "${srcdir:?}/${_name}" || return 1
    git describe --long --tags --abbrev=7 | sed 's/-/.r/;s/-/./'
}

build() {
    cd "${srcdir:?}/${_name}" || return 1
    make
}

package() {
    cd "${srcdir:?}/${_name}" || return 1
    make INSTALL_PREFIX="${pkgdir:?}/usr" install
    install -Dm644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}
