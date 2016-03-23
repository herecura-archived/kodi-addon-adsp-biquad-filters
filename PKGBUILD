# $Id$
# Maintainer: BlackEagle <ike.devolder@gmail.com>>

pkgname=kodi-addon-adsp-biquad-filters
_commit=621866d
pkgver=20160302.621866d
pkgrel=1
pkgdesc=""
arch=('i686' 'x86_64')
url='https://github.com/kodi-adsp/adsp.biquad.filters'
license=('GPL')
groups=('kodi-addons' 'kodi-addons-adsp')
depends=('kodi-platform' 'asplib')
makedepends=('git' 'cmake')
source=("$pkgname::git://github.com/kodi-adsp/adsp.biquad.filters.git#commit=$_commit")
sha256sums=('SKIP')

pkgver() {
	cd "$pkgname"
	git log -1 --date=short --format="%cd.%h" | tr -d '-'
}

build() {
	cd "$pkgname"
	cmake \
		-DCMAKE_INSTALL_PREFIX=/usr \
		-DCMAKE_BUILD_TYPE=Release \
		-DBUILD_SHARED_LIBS=1 \
		-DUSE_LTO=1
	make
}

package() {
	cd "$pkgname"
	make DESTDIR="$pkgdir/" install
}

