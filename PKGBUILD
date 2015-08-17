# Maintainer: Parantapa Bhattacharya <pb at parantapa dot net>
pkgname=ttf-cosmic-sans-neue-git
pkgver=0.r50.315e359
epoch=2
pkgrel=1
pkgdesc="A font family with a great monospaced variant for programmers."
arch=('any')
url="https://github.com/belluzj/cosmic-sans-neue"
license=('SIL OPEN FONT LICENSE Version 1.1')
depends=('fontconfig' 'xorg-font-utils')
makedepends=('git' 'fontforge' 'ttfautohint' 'sfnt2woff' 'ttf2eot')
install=$pkgname.install
source=(git+https://github.com/belluzj/cosmic-sans-neue.git)
md5sums=('SKIP')

pkgver() {
  cd "$srcdir/cosmic-sans-neue"
  printf "0.r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

build() {
    cd "$srcdir/cosmic-sans-neue"
    make
}

package() {
    install -d "${pkgdir}/usr/share/fonts/TTF"
    cp -dpr --no-preserve=ownership "${srcdir}/cosmic-sans-neue/"*.ttf "${pkgdir}/usr/share/fonts/TTF"
}
