# Contributor: Anton Bazhenov <anton.bazhenov at gmail>
# Contributor: Andre Klitzing <aklitzing () online () de>

pkgname=phrasendrescher
pkgver=1.2.2
pkgrel=1
pkgdesc="A modular and multi processing pass phrase cracking tool"
arch=('i686' 'x86_64')
url="http://www.leidecker.info/projects/phrasendrescher/"
license=('BSD')
depends=('openssl' 'libssh2' 'gpgme')
options=('!libtool')
source=(http://www.leidecker.info/projects/$pkgname/$pkgname-$pkgver.tar.gz \
  $pkgname.patch)
md5sums=('3f2093c3415dcaea2110db55c58cecb6'
         'aaa7018d8c9ca036bc706cb4a8b4c428')

build() {
  cd $srcdir/$pkgname-$pkgver
  patch -p0 -i ../$pkgname.patch || return 1
  ./configure --prefix=/usr --with-plugins || return 1
  make || return 1
  make DESTDIR=$pkgdir install || return 1
  install -Dm644 COPYING $pkgdir/usr/share/licenses/$pkgname/COPYING
}
