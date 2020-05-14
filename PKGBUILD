# Maintainer: Matt Gray <Buddy.Matt1984@Gmail.com>
pkgname=monodevelop-versioncontrol-bin
pkgver=7.8.4
pkgrel=1
pkgdesc="MonoDevelop is a GNOME IDE primarily designed for C# and other CLI (.NET) languages"
arch=('x86_64')
license=('MIT')
depends=('monodevelop-bin')
provides=('monodevelop-versioncontrol')
url="https://github.com/mono/monodevelop"

source=("monodevelop-amd64-v${_pkgver}.deb::http://download.mono-project.com/repo/ubuntu/pool/main/m/monodevelop/monodevelop_7.8.4.1-0xamarin6+ubuntu1804b1_amd64.deb")
sha256sums=('e98cf23872aa0cb09fa000dd8f0ef9ad7f03a41a2d28ab1e2f215493bbd073bc')

package() {
    cd "${srcdir}"

    bsdtar xf data.tar.xz
    chmod -R g-w usr
    mv usr "${pkgdir}"
}
