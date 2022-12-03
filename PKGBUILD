# Maintainer: Pellegrino Prevete <pellegrinoprevete@gmail.com>

# shellcheck disable=SC2034
_namespace="tallero"
_pkgbase="soundscope-player"
_pkgname="${_pkgbase}"
pkgname="${_pkgbase}-git"
pkgver=1.0+2+gd7c14a7
pkgrel=1
pkgdesc="Make an audio CD-R image from media files."
arch=('any')
url="https://github.com/${_namespace}/${pkgbase}"
_url="ssh://git@127.0.0.1:/home/git/${pkgbase}"
provides=("${_pkgname}")
conflicts=("${_pkgname}")
depends=('ffmpeg'
         'shntool'
         'python-appdirs')
makedepends=('git'
             'python-setuptools')
license=("AGPL3")
source=("${_pkgname}::git+${_url}")
sha256sums=("SKIP")

pkgver() {
  cd $_pkgname
  git describe --tags | sed 's/-/+/g'
}

package() {
  cd "${_pkgname}" || exit
  python3 setup.py install --root="${pkgdir}" --optimize=1
}