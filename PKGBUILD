pkgname=dwm-custom-git
_pkgname=dwm
pkgver=6.2.34.gb5b2e2d
pkgrel=1
pkgdesc="A dynamic window manager for X; my costom build"
url="http://dwm.suckless.org"
arch=('i686' 'x86_64')
license=('MIT')
options=(zipman)
depends=('libx11' 'libxinerama' 'libxft')
makedepends=('git')
provides=('dwm')
conflicts=('dwm')
epoch=1
source=()
md5sums=()


pkgver(){
  cd ..
  git describe --tags |sed 's/-/./g'
}


build() {
  cd ..
  make X11INC=/usr/include/X11 X11LIB=/usr/lib/X11
}

package() {
  cd ..
  make PREFIX=/usr DESTDIR="$pkgdir" install
  install -m644 -D LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
  install -m644 -D README "$pkgdir/usr/share/doc/$pkgname/README"
  install -m644 -D dwm.desktop "$pkgdir/usr/share/xsessions/dwm.desktop"
}

# vim:set ts=2 sw=2 et:
