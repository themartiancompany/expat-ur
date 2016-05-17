# Maintainer:  Bartłomiej Piotrowski <bpiotrowski@archlinux.org>
# Contributor: Allan McRae <allan@archlinux.org>
# Contributor: Judd Vinet <jvinet@zeroflux.org>

pkgname=expat
pkgver=2.1.1
pkgrel=2
pkgdesc='An XML parser library'
arch=('i686' 'x86_64')
url='http://expat.sourceforge.net/'
license=('custom')
depends=('glibc')
source=(http://downloads.sourceforge.net/sourceforge/expat/$pkgname-$pkgver.tar.bz2
        CVE-2015-1283-refix.patch
        CVE-2016-0718-v2-2-1.patch)
md5sums=('7380a64a8e3a9d66a9887b01d0d7ea81'
         'd54dd69a14bedb86fc6f6e0c0be5c4a4'
         'beb1b2dc1f0d988ed85a5dd30a3b322a')

prepare() {
  cd $pkgname-$pkgver
  patch -p2 < "${srcdir}/CVE-2015-1283-refix.patch"
  patch -p2 < "${srcdir}/CVE-2016-0718-v2-2-1.patch"
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
