# Maintainer: YOUR NAME <YOUR EMAIL>
pkgname=car-monitor
pkgver=1.0.0
pkgrel=1
pkgdesc="Terminal client for the GWES Central Alert Repository API v2"
arch=('any')
url="https://alerts.globaleas.org/"
license=('MIT')
depends=('python' 'python-requests')
source=('car')
sha256sums=('6dd3488fc8f1973497a1345cf4523f2f72310be9aa62c2e25f150474bdbda54f')

package() {
    install -Dm755 "$srcdir/car" "$pkgdir/usr/bin/car"
}
