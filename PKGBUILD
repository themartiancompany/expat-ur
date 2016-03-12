# Maintainer:  Bartłomiej Piotrowski <bpiotrowski@archlinux.org>
# Contributor: Allan McRae <allan@archlinux.org>
# Contributor: Judd Vinet <jvinet@zeroflux.org>

pkgname=expat
pkgver=2.1.1
pkgrel=1
pkgdesc='An XML parser library'
arch=('i686' 'x86_64')
url='http://expat.sourceforge.net/'
license=('custom')
depends=('glibc')
source=(http://downloads.sourceforge.net/sourceforge/expat/$pkgname-$pkgver.tar.bz2)
md5sums=('7380a64a8e3a9d66a9887b01d0d7ea81')

build() {
  cd $pkgname-$pkgver
  ./configure --prefix=/usr
  make
}

check() {
  make -C $pkgname-$pkgver check
}

package() {
  cd $pkgname-$pkgver
  make DESTDIR="$pkgdir" install
  install -Dm644 COPYING "$pkgdir"/usr/share/licenses/$pkgname/COPYING
}
