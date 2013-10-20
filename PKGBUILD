# Maintainer: Allan McRae <allan@archlinux.org>
# Committer: Judd Vinet <jvinet@zeroflux.org>

pkgname=expat
pkgver=2.1.0
pkgrel=3
pkgdesc="An XML parser library"
arch=('i686' 'x86_64')
url="http://expat.sourceforge.net/"
license=('custom')
depends=('glibc')
source=(http://downloads.sourceforge.net/sourceforge/expat/${pkgname}-${pkgver}.tar.gz)
md5sums=('dd7dab7a5fea97d2a6a43f511449b7cd')

build() {
  cd ${srcdir}/${pkgname}-${pkgver}
  ./configure --prefix=/usr
  make
}

check() {
  cd ${srcdir}/${pkgname}-${pkgver}
  make check
}

package() {
  cd ${srcdir}/${pkgname}-${pkgver}
  make DESTDIR=${pkgdir} install
  install -Dm644 COPYING ${pkgdir}/usr/share/licenses/${pkgname}/COPYING
}
