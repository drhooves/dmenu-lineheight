# Maintainer:  Markus Hovorka <m.hovorka@live.de>
# Contributor: Bartłomiej Piotrowski <bpiotrowski@archlinux.org>
# Contributor: Thorsten Töpper <atsutane-tu@freethoughts.de>
# Contributor: Thayer Williams <thayer@archlinux.org>
# Contributor: Jeff 'codemac' Mickey <jeff@archlinux.org>

pkgname=dmenu-lineheight-xyw
pkgver=4.6
pkgrel=1
pkgdesc="A generic menu for X"
url="http://tools.suckless.org/dmenu/"
arch=('i686' 'x86_64')
license=('MIT')
depends=('sh' 'libxinerama' 'libxft' 'freetype2')
provides=('dmenu')
conflicts=('dmenu')
source=("http://dl.suckless.org/tools/dmenu-$pkgver.tar.gz"
        "http://tools.suckless.org/dmenu/patches/dmenu-lineheight-4.6.diff")
md5sums=('6fedf081133bc0725cb040b3b8ac3fac'
         '910a3279e4e4b4007d345e8b572a5eec')

prepare() {
	cd dmenu-$pkgver
	patch -p1 -F 3 < "../dmenu-lineheight-$pkgver.diff"
}

build() {
	cd dmenu-$pkgver
	make X11INC=/usr/include/X11 X11LIB=/usr/lib/X11 FREETYPEINC=/usr/include/freetype2
}

package() {
	cd dmenu-$pkgver
	make PREFIX=/usr DESTDIR="$pkgdir" install
	install -Dm644 LICENSE "$pkgdir"/usr/share/licenses/$pkgname/LICENSE
}
