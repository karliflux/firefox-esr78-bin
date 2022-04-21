# Maintainer: Kitteh Squared <kitteh2 at hotmail dot com>
# Contributor: Charles Samborski <demurgos at demurgos dot net>
# Contributor: Manuel Kauschinger <admin at bruzzzla dot de>
# Contributor: Will Adams <info at clementlumber dot com>
# Contributor: T. Jameson Little <t.jameson.little at gmail dot com>
# Contributor: Stephen Michael <ihateseptictanks at gmail dot com>
# Contributor: Simon Tunnat <simon+aur@tunn.at>
# Contributor: Bartlomiej Piotrowski <nospam@bpiotrowski.pl>

pkgname=firefox-esr52-bin
_pkgname=${pkgname/-bin/}
pkgver=52.9.0
pkgrel=1
pkgdesc='Standalone web browser from mozilla.org - Extended Support Release - Version 52'
url='http://www.mozilla.org/en-US/firefox/organizations/'
arch=('i686' 'x86_64')
depends=('gtk2' 'gtk3' 'libxt' 'dbus-glib' 'nss')
makedepends=()
provides=('firefox=52')
license=('MPL' 'GPL' 'LGPL')
install=$_pkgname.install

sha512sums=('b5d7da00766354e72f5a48f4f2143623428256d79d0b3e958ed6764b680afdf2b3188c61b09a02dd1537c8b8d3ddd1a1b828b1cc13a16df02a52538a42c62954'
            '0842e3dec2239e3a142fb22829e0f2cf751b5bcfce72f2e2baa5bfdb1444f72e7c472e5fdc5eb3e6afc0858b42bc2ffe42808ba7e52243ce330149565eeec26c'
            '46c2dd70e2939baa491cd4049fed371c46ed157fa09ed1a1fca224b670fa63762185043a9a1a8d707b8b234174743e3e03c9e2ac63066ec47c411b8803d6af88')
[[ "$CARCH" == "i686" ]] && sha512sums[0]='f0f6b494eed4f84eb013065ed1a586efb03b50441023fea866306fbb65de3e7ebe5ff572575d868c17e3ca11958d90b1d6a8cffda0babfa8432e4bd3f19eda15'

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
