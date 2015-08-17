# Maintainer: Arch Haskell Team <arch-haskell@haskell.org>
_hkgname=repa-examples
pkgname=repa-examples
pkgver=1.1.1.0
pkgrel=2
pkgdesc="Examples using the Repa array library."
url="http://hackage.haskell.org/package/${_hkgname}"
license=('custom:BSD3')
arch=('i686' 'x86_64')
makedepends=('ghc' 'haskell-random=1.0.0.2' 'haskell-repa<1.2' 'haskell-repa-algorithms<1.2' 'haskell-repa-io<1.2')
depends=('gmp')
options=('strip')
source=(http://hackage.haskell.org/packages/archive/${_hkgname}/${pkgver}/${_hkgname}-${pkgver}.tar.gz)
build() {
    cd ${srcdir}/${_hkgname}-${pkgver}
    runhaskell Setup configure --prefix=/usr --docdir=/usr/share/doc/${pkgname} -O
    runhaskell Setup build
}
package() {
    cd ${srcdir}/${_hkgname}-${pkgver}
    runhaskell Setup copy --destdir=${pkgdir}
    install -D -m644 LICENSE ${pkgdir}/usr/share/licenses/${pkgname}/LICENSE
    rm -f ${pkgdir}/usr/share/doc/${pkgname}/LICENSE
}
md5sums=('babc0243cddb58cf481a2b785301dc08')
