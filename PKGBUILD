# Maintainer:  Bartłomiej Piotrowski <bpiotrowski@archlinux.org>
# Contributor: Allan McRae <allan@archlinux.org>
# Contributor: Judd Vinet <jvinet@zeroflux.org>

pkgname=expat
pkgver=2.2.0
pkgrel=2
pkgdesc='An XML parser library'
arch=('i686' 'x86_64')
url='http://expat.sourceforge.net/'
license=('custom')
depends=('glibc')
source=(http://downloads.sourceforge.net/sourceforge/expat/$pkgname-$pkgver.tar.bz2
        expat-2.2.0-CVE-2016-0718-regression.patch)
md5sums=('2f47841c829facb346eb6e3fab5212e2'
         'dda0b42ed32491577d0b5fb6bf0963be')

prepare() {
  cd $pkgname-$pkgver
  patch -p2 -i "$srcdir"/expat-2.2.0-CVE-2016-0718-regression.patch
}

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
