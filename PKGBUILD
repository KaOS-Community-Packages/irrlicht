pkgname=irrlicht
pkgver=1.8.4
pkgrel=1
pkgdesc="An open source high performance realtime 3D graphics engine."
arch=('x86_64')
url="http://irrlicht.sourceforge.net/"
license=('ZLIB')
depends=('libgl' 'libjpeg-turbo' 'bzip2' 'libpng')
makedepends=('mesa' 'unzip')
source=("http://downloads.sourceforge.net/irrlicht/$pkgname-$pkgver.zip")
md5sums=('9401cfff801395010b0912211f3cbb4f')

build() {
  cd $srcdir/$pkgbase-$pkgver/source/Irrlicht
  make NDEBUG=1 sharedlib
}

package() {
  cd $srcdir/$pkgbase-$pkgver/source/Irrlicht
  sed -i "/^INSTALL_DIR/s:=.*:=$pkgdir/usr/lib:" Makefile
  make install
  chmod 644 $pkgdir/usr/include/$pkgbase/*
  cd $pkgdir/usr/lib
  ln -s libIrrlicht.so.$pkgver libIrrlicht.so.1
}
