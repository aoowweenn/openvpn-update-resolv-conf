# Maintainer:  Alfredo Palhares <masterkorp@masterkorp.net>
# Contributor: Chien Wei-Chen <aoowweenn@gmail.com>
# Contributor: Grigory Sokolik <g.sokol99@g-sokol.info>

pkgname=openvpn-update-resolv-conf-umw
pkgver=27.4a16371
pkgrel=1
pkgdesc="This is a script to update your /etc/resolv.conf with DNS settings that come from the received push dhcp-options. Since network management is out of OpenVPN client scope, this script adds and removes the provided from those settings. This script was found on the OpenVPN page of the Archlinux Wiki"
arch=('any')
url="https://github.com/aoowweenn/openvpn-update-resolv-conf"
license=('GPL')
depends=('openvpn' 'openresolv' 'networkmanager')
makedepends=('git')
install=openvpn-update-resolv-conf-git.install
source=("$pkgname::git+git://github.com/aoowweenn/openvpn-update-resolv-conf.git#branch=umw_dev")
md5sums=('SKIP')

pkgver() {
  cd "$pkgname"
  printf "%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

package() {
  cd "${srcdir}"
  install -Dm0755 "${pkgname}/update-resolv-conf.sh" "${pkgdir}/usr/bin/update-resolv-conf.sh"
  install -Dm0755 "${pkgname}/98-vpn" "${pkgdir}/etc/NetworkManager/dispatcher.d/98-vpn"
}

# vim: set ts=2 sw=2 et:
