# Maintainer: tunaflsh <tunaflish.ai@gmail.com>
pkgname=xremap-socket-bin
pkgdesc='Dynamic key remapper for X11 and Wayland (Socket Version)'
pkgver=0.15.9
pkgrel=1

provides=('xremap')
license=('MIT')
url='https://github.com/xremap/xremap'
arch=('x86_64' 'aarch64')
options=('!debug')

source=("LICENSE-$pkgver::https://raw.githubusercontent.com/xremap/xremap/v$pkgver/LICENSE")
sha256sums=('60365594c733128ba50f05de00c4a6f07fed0a6e8bbd93817f39ded3980f7343')

source_x86_64=("$pkgname-$pkgver-x86_64.zip::https://github.com/xremap/xremap/releases/download/v$pkgver/xremap-linux-x86_64-socket.zip")
sha256sums_x86_64=('145f4115bc9fdfe4a2f5b7768f4112092d96ef019141542ea369a159d70c4392')

source_aarch64=("$pkgname-$pkgver-aarch64.zip::https://github.com/xremap/xremap/releases/download/v$pkgver/xremap-linux-aarch64-socket.zip")
sha256sums_aarch64=('b8a49c799a85a13df55bf5bb2c1c6dfdd21a7b0b5e24bed8df1bd9f928e7fe29')

package() {
	cd "$srcdir/"
	./xremap --completions zsh > zsh_completions
	./xremap --completions fish > fish_completions
	./xremap --completions bash > bash_completions
	install -Dm644 zsh_completions "${pkgdir}/usr/share/zsh/site-functions/_xremap"
	install -Dm644 fish_completions "${pkgdir}/usr/share/fish/vendor_completions.d/xremap.fish"
	install -Dm644 bash_completions "${pkgdir}/usr/share/bash-completion/completions/xremap"
	install -Dm755 xremap "${pkgdir}/usr/bin/xremap"
	install -Dm644 "LICENSE-$pkgver" "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}
