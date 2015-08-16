# Maintainer: Gustavo Alvarez <s1pkn07@gmail.com>
# Contributor: Kristjan Reinloo <mail at kreinloo dot net>
# Contributor: Pierre Bourdon <delroth@gmail.com>

pkgname=libnatpmp
pkgver=20131126
pkgrel=1
pkgdesc="A portable and fully compliant implementation of the NAT-PMP protocol"
arch=('i686' 'x86_64')
url="http://miniupnp.free.fr/libnatpmp.html"
license=('custom')
depends=('glibc')
source=("http://miniupnp.tuxfamily.org/files/libnatpmp-${pkgver}.tar.gz")
sha1sums=('604a620fa38e0681d4822400156db2daaee954d1')

prepare() {
  rm -fr build
  cp -R "${pkgname}-${pkgver}" build
}

build() {
  cd build
  make
}

package() {
  cd build
  make INSTALLPREFIX="${pkgdir}/usr" INSTALLDIRINC="${pkgdir}/usr/include" install
  install -Dm644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}
