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
# TODO: Check for when 15 releases and use that
depends=('postgresql>=14.0' 'postgresql<15.0')
makedepends=()
provides=()
conflicts=()
install="script.install"
package() {
  # noop
  true
}
