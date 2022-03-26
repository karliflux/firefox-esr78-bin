# Maintainer: Kitteh Squared <kitteh2 at hotmail dot com>
# Contributor: Charles Samborski <demurgos at demurgos dot net>
# Contributor: Manuel Kauschinger <admin at bruzzzla dot de>
# Contributor: Will Adams <info at clementlumber dot com>
# Contributor: T. Jameson Little <t.jameson.little at gmail dot com>
# Contributor: Stephen Michael <ihateseptictanks at gmail dot com>
# Contributor: Simon Tunnat <simon+aur@tunn.at>
# Contributor: Bartlomiej Piotrowski <nospam@bpiotrowski.pl>

pkgname=firefox-esr78-bin
_pkgname=${pkgname/-bin/}
pkgver=78.15.0
pkgrel=1
pkgdesc='Standalone web browser from mozilla.org - Extended Support Release - Version 78'
url='http://www.mozilla.org/en-US/firefox/organizations/'
arch=('i686' 'x86_64')
depends=('gtk2' 'gtk3' 'libxt' 'dbus-glib' 'nss')
makedepends=()
provides=('firefox=78')
license=('MPL' 'GPL' 'LGPL')
install=$_pkgname.install

sha512sums=('5c7bb23a9003f4e246a40e54613873051a640ae2a69da60a241e48f8fe413095c46182a8626344caaa3efd4620f9100c2656967106056aa5db9a646fed1bb57e'
            '0842e3dec2239e3a142fb22829e0f2cf751b5bcfce72f2e2baa5bfdb1444f72e7c472e5fdc5eb3e6afc0858b42bc2ffe42808ba7e52243ce330149565eeec26c'
            '46c2dd70e2939baa491cd4049fed371c46ed157fa09ed1a1fca224b670fa63762185043a9a1a8d707b8b234174743e3e03c9e2ac63066ec47c411b8803d6af88')
[[ "$CARCH" == "i686" ]] && sha512sums[0]='069b0faa92408adc319527eb3d6cb462f122156a507b3c646bf9a467fb49e5f2b48cc4a2d1dd7f55d8b7f2c6e279d3768100a668e95153ac6467fcc7ff8f94b4'

source=(https://ftp.mozilla.org/pub/firefox/releases/${pkgver}esr/linux-$CARCH/en-US/firefox-${pkgver}esr.tar.bz2
        $_pkgname.desktop 
        $_pkgname-safe.desktop)

package() {
    cd $srcdir
    
    install -d $pkgdir/{usr/{bin,share/{applications,pixmaps}},opt}
    cp -r firefox/ $pkgdir/opt/$_pkgname

    ln -s /opt/$_pkgname/firefox $pkgdir/usr/bin/$_pkgname
    install -m644 $srcdir/{$_pkgname.desktop,$_pkgname-safe.desktop} $pkgdir/usr/share/applications/
    install -m644 $srcdir/firefox/browser/chrome/icons/default/default128.png $pkgdir/usr/share/pixmaps/$_pkgname.png
}
