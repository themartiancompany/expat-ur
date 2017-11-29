# Maintainer:  Bartłomiej Piotrowski <bpiotrowski@archlinux.org>
# Contributor: Allan McRae <allan@archlinux.org>
# Contributor: Judd Vinet <jvinet@zeroflux.org>

pkgname=expat
pkgver=2.2.5
pkgrel=1
pkgdesc='An XML parser library'
arch=(x86_64)
url='https://libexpat.github.io/'
license=(custom)
depends=(glibc)
source=(https://github.com/libexpat/libexpat/releases/download/R_${pkgver//./_}/$pkgname-$pkgver.tar.bz2)
sha256sums=('d9dc32efba7e74f788fcc4f212a43216fc37cf5f23f4c2339664d473353aedf6')

build() {
  cd $pkgname-$pkgver
  ./configure --prefix=/usr --disable-static
  make
}

check() {
  make -C $pkgname-$pkgver check
}

package() {
  cd $pkgname-$pkgver
  make DESTDIR="$pkgdir" install
  install -Dm644 "-t$pkgdir/usr/share/licenses/$pkgname" COPYING
}
