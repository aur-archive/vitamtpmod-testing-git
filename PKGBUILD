# Maintainer: codestation <codestation404@gmail.com>

pkgname=vitamtpmod-testing-git
_pkgname=VitaMTP
pkgver=20140503
pkgrel=1
pkgdesc="Library to interact with Vita's USB MTP protocol (fork)"
arch=("i686" "x86_64")
url="https://github.com/codestation/VitaMTP"
license=('GPL')
depends=('libusb' 'libxml2')
conflicts=('vitamtp' 'vitamtp-git' 'vitamtpmod-git')
source=('git://github.com/codestation/VitaMTP.git#branch=testing')
options=('!libtool')
md5sums=('SKIP')

build() {
  cd "$srcdir/$_pkgname"

  ./autogen.sh
  ./configure --prefix=/usr
  make
}

package() {
  cd "$srcdir/$_pkgname"
  make DESTDIR="${pkgdir}" install
  install -Dm644 debian/vitamtp3.udev "$pkgdir/usr/lib/udev/rules.d/80-psvita.rules"
}
