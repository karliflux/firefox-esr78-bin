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
            '5993fc02493c7a81b867153f533a0ef9b411c89b7dcdfe1d565282ba5043f9d3f3d26b2826511bbb32422024c76490b64a64c686d71d107b271f6b0bbfa2d4ec'
            '78fd236775978c23f64bdb13c9e242e36b6195fc86ace8b703569835398c95bd9e535399317d8bb2060f6f058d9a3e9217cb77739edc1a1d950a7e1b7fe5b870')
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
