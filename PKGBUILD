# SPDX-License-Identifier: AGPL-3.0
#
# Maintainer: Truocolo <truocolo@aol.com>
# Maintainer: Pellegrino Prevete <cGVsbGVncmlub3ByZXZldGVAZ21haWwuY29tCg== | base -d>
# Contributor: Nikita Ukhrenkov <thekit@disroot.org>

_proj="maemo-leste"
pkgname=libhildonfm
pkgver=2.28.27
_commit="af37385e2a915bccb3a1a7b725dfcbac70b4de84"
pkgrel=1
pkgdesc="Hildon file management libraries"
_http="https://github.com"
_ns="${_proj}"
url="${_http}/${_ns}/${pkgname}"
arch=(
  arm
  aarch64
  i686
  x86_64
)
license=(
  LGPL
)
depends=(
  libhildon
  xdg-user-dirs
) 
makedepends=(
  autoconf
  automake
  gconf
  hildon-thumbnail
  libpng
  libosso
  libhildonmime
  libtool
  m4
  mce-headers
)
checkdepends=()
groups=(
  hildon
)
_tag="${pkgver}"
_obj="tag"
[[ "${_commit}" != "" ]] && \
  _tag="${_commit}" \
  _obj="commit"
_tarname="${pkgname}-${_tag}"
provides=(
  "${pkgname}-leste=${pkgver}"
  "${pkgname}-maemo-leste=${pkgver}"
)
source=(
  "${_tarname}::git+${url}.git#${_obj}=${_tag}"
)
sha256sums=(
  'SKIP'
)

build() {
  cd \
    "${_tarname}"
  ./autogen.sh 
  ./configure \
    --prefix=/usr
  make
 }

package() {
  cd \
    "${_tarname}"
  make \
    DESTDIR="${pkgdir}" \
    install
  rm \
    "${pkgdir}/etc/xdg/user-dirs.defaults"
}

# vim: ft=sh syn=sh et
