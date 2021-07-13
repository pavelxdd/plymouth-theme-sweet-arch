# Maintainer: Abraham Murciano <abrahammurciano[at]gmail[dot]com>
# Maintainer: Pavel Otchertsov <pavel.otchertsov[at]gmail[dot]com>

_theme="sweet-arch"
_pkgname="plymouth-theme-$_theme"
pkgname="$_pkgname-git"
pkgver=2.1.r2.ga3e3907
pkgrel=1
pkgdesc="Make your Arch Linux splash screen look wonderful"
arch=("any")
url="https://github.com/pavelxdd/$_pkgname"
license=("GPL")
depends=("plymouth")
makedepends=("git")
source=("$_pkgname::git+https://github.com/pavelxdd/$_pkgname.git")
sha256sums=("SKIP")

pkgver() {
    cd "$srcdir/$_pkgname"
    git describe --long --tags | sed 's/^v//;s/\([^-]*-g\)/r\1/;s/-/./g'
}

package() {
    cd "$srcdir/$_pkgname/$_theme"
    install -m755 -d "${pkgdir}/usr/share/plymouth/themes/$_theme"
    install -m644 -t "${pkgdir}/usr/share/plymouth/themes/$_theme" *
}
