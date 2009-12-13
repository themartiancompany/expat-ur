# Maintainer: dorphell <dorphell@archlinux.org>
# Committer: Judd Vinet <jvinet@zeroflux.org>

pkgname=expat
pkgver=2.0.1
pkgrel=3
pkgdesc="An XML Parser library written in C"
arch=('i686' 'x86_64')
url="http://expat.sourceforge.net/"
license=('custom')
depends=('glibc')
options=('!libtool')
source=(http://downloads.sourceforge.net/sourceforge/expat/${pkgname}-${pkgver}.tar.gz
        CVE-2009-3560.patch)
md5sums=('ee8b492592568805593f81f8cdf2a04c'
         '50aa6f7693fda07f4720a0495d12e695')

build() {
  cd "${srcdir}/${pkgname}-${pkgver}"
  patch -Np1 -i $srcdir/CVE-2009-3560.patch
  ./configure --prefix=/usr --mandir=/usr/share/man || return 1
  make || return 1
  make DESTDIR="${pkgdir}" install || return 1
  install -Dm644 COPYING "${pkgdir}/usr/share/licenses/${pkgname}/COPYING" || return 1
}
