# Maintainer: Yunus Emre YOLDAŞ <yoldas.emre@anticverse.com>
pkgname=tgbot-cpp-static
pkgver=99999
pkgrel=0
_commit=782596206764e663b9b45401b447871f21ce62b2
pkgdesc="Static Telegram bot API in c++"
url="https://github.com/reo7sp/tgbot-cpp"
arch="all"
license="MIT"
depends=""
builddir=tgbot-cpp-$_commit
makedepends="cmake boost-dev openssl-dev zlib-dev curl-dev"
source="
	$pkgname-$pkgver.tar.gz::https://github.com/reo7sp/tgbot-cpp/archive/$_commit.tar.gz
	"

build() {
  cmake -DCMAKE_INSTALL_PREFIX=/usr .
  make
}

package() {
  cd "src/tgbot-cpp-$_commit"
  make DESTDIR="$pkgdir" install 
}

sha512sums="
ad79dd9d11186e60030534511eefddc5c00aa5f0c3d2fad2b0418c76e85627d3b288c400abfe0af3e60f8fb795d60aa57ace831133df7958fbfb6c5ce7ccb180  tgbot-cpp-static-99999.tar.gz
"
