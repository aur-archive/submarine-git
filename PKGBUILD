# Maintainer: murchik <mixturchik@gmail.com>

pkgname=submarine-git
_gitname=submarine
pkgver=0.1.5
pkgrel=2
pkgdesc="Command-line program for searching and downloading the right subtitles for movies"
arch=('i686' 'x86_64')
license=('LGPL')
url="https://github.com/rastersoft/submarine"
depends=('glib2' 'libgee' 'libsoup' 'libarchive' 'unzip')
makedepends=('vala' 'git' 'libtool' 'automake' 'autoconf' 'cmake')
optdepends=('imagemagick: for external commands'
			'libjpeg-turbo: for external commands'
			'gimp: open with')
provides=('submarine')
conflicts=('submarine')
source=("git+https://github.com/rastersoft/submarine.git")
md5sums=('SKIP')

pkgver() {
  cd "$srcdir/$pkgname"
  git describe --long | sed -E 's/([^-]*-g)/r\1/;s/-/./g'
}

build() {
	cd "${srcdir}/${_gitname}"
	cmake -DCMAKE_INSTALL_PREFIX=/usr .
	make -j1
}

package() {
	cd "${srcdir}/${_gitname}"
  	make DESTDIR="${pkgdir}" install
} 
