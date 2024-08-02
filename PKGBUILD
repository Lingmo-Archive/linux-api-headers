pkgname=linux-api-headers
pkgver=6.10
pkgrel=1
pkgdesc='Kernel headers sanitized for use in userspace'
arch=('x86_64')
url='https://www.gnu.org/software/libc'
license=(GPL-2.0-only)
makedepends=(rsync)
source=(git+https://github.com/LingmoOS/linux-kernel)
sha256sums=('SKIP')
validpgpkeys=('ABAF11C65A2970B130ABE3C479BE3E4300411886'   # Linus Torvalds
              '647F28654894E3BD457199BE38DBBDC86092693E'   # Greg Kroah-Hartman
              '41EF7182553A87AC18196A77F27F2FDA54F067D8') # Lingmo OS Team <team@lingmo.org>

build() {
  cd linux-kernel

  make mrproper
}

package() {
  cd linux-kernel
  make INSTALL_HDR_PATH="$pkgdir/usr" headers_install

  # use headers from libdrm
  rm -r "$pkgdir/usr/include/drm"
}
