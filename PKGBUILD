pkgname=postgresql-config-grug
pkgver=0.0.1
pkgver() {
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}
pkgrel=1
arch=('any')
pkgdesc="postgresql config for grug"
url="https://git.grug.se/admin/postgresql-config-grug"
license=('MIT')
depends=('postgresql')
makedepends=()
provides=()
conflicts=()
install="script.install"
package() {
  # noop
  true
}
