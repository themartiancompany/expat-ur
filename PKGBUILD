# Maintainer:  Bartłomiej Piotrowski <bpiotrowski@archlinux.org>
# Contributor: Allan McRae <allan@archlinux.org>
# Contributor: Judd Vinet <jvinet@zeroflux.org>

pkgname=expat
pkgver=2.2.5
pkgrel=1
pkgdesc='An XML parser library'
arch=(x86_64)
url='http://expat.sourceforge.net/'
license=(custom)
depends=(glibc)
source=(http://downloads.sourceforge.net/sourceforge/expat/$pkgname-$pkgver.tar.bz2)
md5sums=('789e297f547980fc9ecc036f9a070d49')

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
  install -Dm644 COPYING "$pkgdir/usr/share/licenses/$pkgname/COPYING"
}
