# $Id: PKGBUILD 57898 2011-11-04 08:59:22Z lcarlier $
# Maintainer: Laurent Carlier <lordheavym@gmail.com>
# Maintainer: Sven-Hendrik Haase <sh@lutzhaase.com>
# Contributor: Arkham <arkham at archlinux dot us>
# Contributor: rabyte <rabyte*gmail>
# Contributor: Andres Blanc <andresblanc@gmail.com>

pkgname=egoboo-data
pkgver=2.8.1
pkgrel=2
arch=('any')
license=('GPL')
pkgdesc="Egoboo data files"
url="http://egoboo.sourceforge.net/"
source=(http://downloads.sourceforge.net/egoboo/egoboo-$pkgver.tar.gz)
md5sums=('e6f3130695d297dcd9fe74e50bd59b68')

build() {
    cd "$srcdir/egoboo-$pkgver"

    # Patch default depth to 24 and sound
    sed -i -e 's/\[COLOR_DEPTH\] : "32"/\[COLOR_DEPTH\] : "24"/g' \
        -e 's/\[Z_DEPTH\] : "32"/\[Z_DEPTH\] : "24"/g' \
        -e 's/\[OUTPUT_BUFFER_SIZE\] : "2548/\[OUTPUT_BUFFER_SIZE\] : "2048/g' \
        setup.txt

    # Copy data and fix permissions
    install -d ${pkgdir}/usr/share/egoboo
    cp -rf controls.txt setup.txt basicdat/ modules/ ${pkgdir}/usr/share/egoboo/
    find ${pkgdir}/usr/share/egoboo -type f -exec chmod 644 {} +
}

