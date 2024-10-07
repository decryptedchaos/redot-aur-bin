# Maintainer: decryptedchaos <nixgod@gmail.com>

_pkgname="redot"
pkgname=${_pkgname}-bin
pkgver=4.4.dev
pkgrel=1
pkgdesc="A multi-platform 2D and 3D game engine"
arch=('x86_64')
url="https://github.com/Redot-Engine/redot-engine"
license=('MIT')
depends=(embree3 freetype2 graphite harfbuzz harfbuzz-icu libglvnd libspeechd
    libsquish libtheora libvorbis libwebp libwslay libxcursor libxi
    libxinerama libxrandr mbedtls2 miniupnpc pcre2)
optdepends=('pipewire-alsa: for audio support'
    'pipewire-pulse: for audio support')
makedepends=(git alsa-lib scons wayland yasm)
source=(
    "redot.linuxbsd.editor."${arch}
    Redot.desktop
    icon.png
    LICENSE.txt
)
sha256sums=('4f31bd1ad96c5066d3117b7c55d56f314e2d4615fc383f56de35935e02ebe718'
            'fef6f824be78059b57e9e66f6fcbae391ae9d023825d826b8da7045935b01a76'
            'abea13996f5744eac9211623266ea1f95fb3c40b0fda8fa2c90d9bf1b790eb60'
            '5e041f35e0430c0dd5667e0f1294602f1211615297a6f09e1cffba7d6081e892')

prepare() {
    if [ -d "$srcdir/$pgnname" ]
    then
        rm -rf "$pkgname"
    fi

    mkdir "$pkgname"
}

build() {

    cp redot.linuxbsd.editor.${arch} ${pkgname}/redot44
    cp icon.png "$pkgname"/
    cp LICENSE.txt "$pkgname"/
    cp Redot.desktop "$pkgname"/
}

# check() {
#     if -d "$pkgname"
#         rm -rf "$pkgname"
#
# }

package() {
	cd "$pkgname"
	 install -Dm644 Redot.desktop ${pkgdir}/usr/share/applications/Redot.desktop
	 install -Dm644 icon.png ${pkgdir}/usr/share/pixmaps/Redot.png
     install -D -m755 redot44 ${pkgdir}/usr/bin/redot44
     install -D -m644 LICENSE.txt ${pkgdir}/usr/share/licenses/"${pkgname}"/LICENSE
}
