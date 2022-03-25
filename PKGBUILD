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
pkgver=78.9.0
pkgrel=1
pkgdesc='Standalone web browser from mozilla.org - Extended Support Release - Version 78'
url='http://www.mozilla.org/en-US/firefox/organizations/'
arch=('i686' 'x86_64')
depends=('gtk2' 'gtk3' 'libxt' 'dbus-glib' 'nss')
makedepends=()
provides=('firefox=78')
license=('MPL' 'GPL' 'LGPL')
install=$_pkgname.install

sha512sums=('8cd9ade31ce2feac752b24f437ad49db6f64ff662d355d3a3257e3d7448901807f7f28c8f33b6800b41ecb494b225d32568f3e7373c0b7701bab78374501a232'
            '41b97f897c66de01a5a1432bd3d5892783be91fd2f1f65725db7232809fbfbe3093ca22ce1600b036384b7c23dd72ea6bbc00c0cdbb9c58d8fab4d201fe8d2f8'
            '5743ac190da932d13d4fec20f9239c8a5629ecad9c86365d939949d0ecf32028897fa6a0dd5570a288235245a98cb3cea4c8c9daddfea60be50455e54b343ebd')
[[ "$CARCH" == "i686" ]] && sha512sums[0]='4a63e6dfbd830d48ecc722e0cbf8256e9f14171cf1331805a1067e01d804b974074640bee42ba0ea4fc036614cc447eda046d6d563c24897eee18d752620f397'

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
