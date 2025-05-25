# Maintainer: willemw <willemw12@gmail.com>

pkgname=simg2img-git
pkgver=r54.a6fcc0f
pkgrel=1
pkgdesc="Convert Google Android factory image to .img file"
arch=('any')
url="https://github.com/anestisb/android-simg2img"
license=('Unknown')
depends=('zlib')
makedepends=('git' 'make')
provides=(${pkgname%-git})
conflicts=(${pkgname%-git})
source=($pkgname::git+https://github.com/anestisb/android-simg2img.git)
md5sums=('SKIP')

pkgver() {
  cd $srcdir/$pkgname
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

build() {
  cd $srcdir/$pkgname
  make
}

package() {
  cd $srcdir/$pkgname
 
  install -Dm755 simg2img     "$pkgdir/usr/bin/simg2img"
  install -Dm755 simg2simg    "$pkgdir/usr/bin/simg2simg"
  install -Dm755 img2simg     "$pkgdir/usr/bin/img2simg"
  install -Dm755 append2simg  "$pkgdir/usr/bin/append2simg"
  install -Dm644 lib*.a       "$pkgdir/usr/lib/lib${_pkgname}.a"
  install -Dm644 include/sparse/sparse.h "$pkgdir/usr/include/sparse/sparse.h"  
}
