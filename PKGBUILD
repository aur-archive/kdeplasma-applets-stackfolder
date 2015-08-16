# Maintainer: palmtree5
# Contributor: imrahil (Hugo Lobo) <hugo_alobo@hotmail.com>
pkgname=kdeplasma-applets-stackfolder
pkgver=2.4
pkgrel=2

original_pkgname='plasma-applet-stackfolder'
original_pkgrel=7

pkgdesc="Browse the stack of folders"
arch=('i686' 'x86_64')
url="http://www.rosalab.com"
license="GPL"
makedepends=('cmake' 'automoc4')
replaces=('kdeplasma-addons-applets-stackfolder')
source=(http://mirror.rosalab.ru/rosa2012.1/repository/SRPMS/main/updates/$original_pkgname-$pkgver-$original_pkgrel.src.rpm)
md5sums=('ef740d0832d390d3df3283d3e0de7087')
build() {
	cd "$srcdir"
        tar -zxvf $original_pkgname-$pkgver.tar.gz
	cd  $original_pkgname-$pkgver
	rm -rf build
	mkdir build
	cd build
	cmake -DCMAKE_INSTALL_PREFIX=`kde4-config --prefix` ../
	make clean
	make VERBOSE=1 || return 1
	make DESTDIR="$pkgdir" install || return 1
}
