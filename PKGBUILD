# Maintainer: BlackEagle <ike.devolder@gmail.com>>

pkgname=kodi-addon-screensaver-asteroids
epoch=1
pkgver=2.2.0
_codename=Leia
pkgrel=1
pkgdesc="Asteroids screensaver for Kodi"
arch=('x86_64')
url='https://github.com/xbmc/screensaver.asteroids'
license=('GPL')
groups=('kodi-addons' 'kodi-addons-screensaver')
depends=('kodi')
makedepends=('cmake' 'kodi-dev')
source=("$pkgname-$pkgver.tar.gz::https://github.com/xbmc/screensaver.asteroids/archive/$pkgver-$_codename.tar.gz")
sha512sums=('12ae16d4c2e89e4407daa5512b67a9589b0bdd06141b2538f1dac47bfd3cdfe831384ac5c66248f53e5e4220160206e89202965b369b353fedb691ea21ade73c')

build() {
    cd "screensaver.asteroids-$pkgver-$_codename"
	cmake \
		-DCMAKE_INSTALL_PREFIX=/usr \
		-DCMAKE_BUILD_TYPE=Release \
		-DBUILD_SHARED_LIBS=1 \
		-DUSE_LTO=1
	make
}

package() {
    cd "screensaver.asteroids-$pkgver-$_codename"
	make DESTDIR="$pkgdir/" install
}

