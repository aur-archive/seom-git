# Maintainer: Frederik "Freso" S. Olesen <freso.dk@gmail.com>
# Contributor: Juan Diego Tascón

_gitname='seom'
pkgname=$_gitname-git
pkgver=201.b30306d
pkgrel=2
pkgdesc="Helper library for yukon, a screencapture solution for gaming."
arch=(i686 x86_64)
license=('GPL')
url='https://github.com/wereHamster/seom/wiki'
depends=('libgl' 'libx11')
makedepends=('git' 'yasm')
conflicts=('seom')
provides=('seom' 'seom-svn')
replaces=('seom-svn')
source=("$_gitname::git+https://github.com/wereHamster/$_gitname.git")
md5sums=('SKIP')

pkgver() {
  cd "$_gitname"
  echo $(git rev-list --count HEAD).$(git rev-parse --short HEAD)
}

build() {
  cd "$_gitname"

  ./configure --prefix="/usr"
  make
}

package() {
  cd "$_gitname"
  make DESTDIR="$pkgdir" install
}

# vim:syntax=sh
