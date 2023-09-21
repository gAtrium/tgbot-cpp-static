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
	static_build.patch
	"

prepare() {
	patch -p1 -i "$srcdir/static_build.patch"
}
build() {
  cmake -DCMAKE_INSTALL_PREFIX=/usr .
  make
}

package() {
  cd "src/tgbot-cpp-$_commit"
  make DESTDIR="$pkgdir" install

  # Install the 'include' directory to /usr/include
  install -d "$pkgdir"/usr/include
  cp -r include/* "$pkgdir"/usr/include/
}

sha512sums="
ad79dd9d11186e60030534511eefddc5c00aa5f0c3d2fad2b0418c76e85627d3b288c400abfe0af3e60f8fb795d60aa57ace831133df7958fbfb6c5ce7ccb180  tgbot-cpp-static-99999.tar.gz
6c4ab4bbaf34535a3bf08455393601f3a9b7f7d0940ad1039426a514fa63716fb49ecd148d46f44ca31b26537567667884c548b288020bb22b05fbd3ff0d20b9  static_build.patch
"
