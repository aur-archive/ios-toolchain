# Maintainer: yetist <yetist@gmail.com>
pkgname=ios-toolchain
pkgver=1.1
pkgrel=1
pkgdesc="A simple and clean ios toolchain based on llvm/clang under linux(cctools-836,ld64-134.9)"
arch=('i686' 'x86_64')
url="http://code.google.com/p/ios-toolchain-based-on-clang-for-linux"
license=('GPL')
makedepends=('llvm' 'clang')
optdepends=('ldid' 'proj2make')
source=("http://ios-toolchain-based-on-clang-for-linux.googlecode.com/files/$pkgname-$pkgver.tar.bz2")
md5sums=('671aa3257f4e95d991fcb02393bac461')

build() {
  cd "$srcdir/$pkgname-$pkgver"

  export CC=clang
  export CXX=clang++
  export CFLAGS=-fno-stack-protector
  export CXXFLAGS=-fno-stack-protector

  ./configure --target=arm-apple-darwin11 --prefix=/usr
  make
}

package() {
  cd "$srcdir/$pkgname-$pkgver"
  export CC=clang
  export CXX=clang++
  export CFLAGS=-fno-stack-protector
  export CXXFLAGS=-fno-stack-protector

  make DESTDIR="$pkgdir/" install
}

# vim:set ts=2 sw=2 et:
