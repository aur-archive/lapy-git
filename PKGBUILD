# Maintainer:  Timofey Titovets <Nefelim4ag@gmail.com>

pkgname=lapy-git
pkgdesc="Special script for including python code in LaTeX"
pkgver=r4.ded6b11
pkgrel=1
url=http://github.com/kai3341/lapy
arch=('any')
makedepends=('python' 'empty')
source=(lapy::git+git://github.com/kai3341/lapy.git)
md5sums=('SKIP')

pkgver() {
  cd "$srcdir/lapy"
  ( set -o pipefail
    git describe --long --tags 2>/dev/null | sed 's/\([^-]*-g\)/r\1/;s/-/./g' ||
    printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
  )
}

package() {
  cd "${srcdir}/lapy"
  mv ./package/usr ${pkgdir}/usr
}
