# Maintainer: Bernhard Landauer <bernhard@manjaro.org>

pkgname=nemo-qml-plugin-dbus
pkgver=2.1.39
pkgrel=1
pkgdesc="Nemo Mobile D-Bus QML Plugin."
arch=('x86_64' 'aarch64')
url="https://github.com/sailfishos/nemo-qml-plugin-dbus"
license=('BSD-3-Clause AND LGPL-2.1-or-later')
depends=('qt6-base' 'qt6-declarative')
provides=('libnemodbus.so=2')
source=("$pkgname-$pkgver.tar.gz::$url/archive/refs/tags/$pkgver.tar.gz")
sha256sums=('b38e14e998b7acc3f6e4a6db51f9e68ac43d0ac36dd6e8ff0146fb1b86b7fb49')

build() {
  cd "$pkgname-$pkgver"
  qmake6 "VERSION=$pkgver" src
  make
}

package() {
  cd "$pkgname-$pkgver"
  make INSTALL_ROOT="${pkgdir}" install
  install -Dm644 license.bsd -t "${pkgdir}/usr/share/licenses/$pkgname/"
}
