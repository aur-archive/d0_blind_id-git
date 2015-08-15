pkgname=d0_blind_id-git
pkgver=r129.834b51b
pkgrel=1
pkgdesc="Cryptographic library for identification with Schnorr ID scheme and Blind RSA Signatures"
arch=('i686' 'x86_64')
url="http://github.com/divVerent/d0_blind_id"
license=('BSD')
depends=('gmp')
makedepends=('git')
source=("git+https://github.com/divVerent/d0_blind_id.git")
md5sums=('SKIP')

pkgver() {
  cd "$srcdir/d0_blind_id"
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

build() {
  cd "$srcdir/d0_blind_id"
  sh autogen.sh
  ./configure --prefix=/usr
  make
}

package() {
  cd "$srcdir/d0_blind_id"
  make DESTDIR="$pkgdir/" install
  install -Dm644 COPYING "$pkgdir"/usr/share/licenses/$pkgname/COPYING
} 
