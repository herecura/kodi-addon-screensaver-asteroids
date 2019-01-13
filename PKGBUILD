# Maintainer: BlackEagle <ike.devolder@gmail.com>>

pkgname=kodi-addon-screensaver-asteroids
epoch=1
pkgver=2.1.0
_codename=Leia
pkgrel=6
pkgdesc="Asteroids screensaver for Kodi"
arch=('x86_64')
url='https://github.com/xbmc/screensaver.asteroids'
license=('GPL')
groups=('kodi-addons' 'kodi-addons-screensaver')
depends=('kodi')
makedepends=('cmake' 'kodi-dev')
source=("$pkgname-$pkgver.tar.gz::https://github.com/xbmc/screensaver.asteroids/archive/$pkgver-$_codename.tar.gz")
sha512sums=('61d848aa136ab3a9896446d92c5bc8d02867bcdc67b8eed58cff0b9c3573c52a19b4d16de5494dc45c0f69946075749d73e8681858d534f8cbbe31d005a9a5c3')

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

