# Maintainer: Aerian Bigshans <wo199710@hotmail.com>
pkgname=ppet-bin
pkgver=1.2.1
pkgrel=1
pkgdesc="Put a moe girl on your desktop"
arch=('x86_64')
url="https://github.com/zenghongtu/PPet"
license=('MIT')
provides=(ppet)
source=("https://github.com/zenghongtu/PPet/releases/download/v${pkgver}/PPet-${pkgver}.deb")
sha256sums=('36933e831609f7d88fe2c689edf91e4a1335a0a569a36c5c5f6b7bb0c72ed90e')
validpgpkeys=()

package() {
    tar xvf "${srcdir}/data.tar.xz"
    install -d  "$pkgdir/opt"
    install -d "$pkgdir/usr"
    install -d "$pkgdir/usr/bin"
    cp -R "$srcdir/usr" "$pkgdir"
    cp -R "$srcdir/opt" "$pkgdir"
    
    find "$pkgdir/opt/PPet" -type f -exec chmod 644 {} \;
    chmod 755 "$pkgdir/opt/PPet/ppet"
    chmod 755 -R "$pkgdir/opt/PPet/resources"
    chmod 4755 "$pkgdir/opt/PPet/chrome-sandbox"

    ln -sf /opt/PPet/ppet "$pkgdir/usr/bin/ppet"
}
