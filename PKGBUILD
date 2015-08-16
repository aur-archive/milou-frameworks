# Contributor: Antonio Rojas

pkgname=milou-frameworks
pkgver=5.0.0
pkgrel=1
pkgdesc="A dedicated search application built on top of Baloo"
arch=('i686' 'x86_64')
url='https://projects.kde.org/projects/kde/workspace/milou/'
license=('LGPL')
depends=('krunner')
makedepends=('extra-cmake-modules' 'kdoctools')
source=("http://download.kde.org/stable/plasma/$pkgver/milou-$pkgver.tar.xz")
md5sums=('ba14efbb53a25918d95335e4fef44749')

prepare() {
  mkdir -p build
}

build() {
  cd build
  cmake ../milou-$pkgver \
    -DCMAKE_BUILD_TYPE=Release \
    -DCMAKE_INSTALL_PREFIX=/opt/kf5 \
    -DLIB_INSTALL_DIR=lib \
    -DQML_INSTALL_DIR=lib/qt/qml
  make
}

package() {
  cd build
  make DESTDIR="${pkgdir}" install
}
