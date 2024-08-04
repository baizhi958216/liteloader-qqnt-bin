# Maintainers: kobe-koto <admin[at]koto.cc>, Ketal_Q_ray <k[at]ketal.icu>
pkgname="liteloader-qqnt-bin"
_pkgname="LiteLoaderQQNT"
pkgver=1.2.0
pkgrel=3
pkgdesc="轻量, 简洁, 开源的 QQNT 插件加载器"
arch=('any')
url="https://github.com/LiteLoaderQQNT/LiteLoaderQQNT"
license=('MIT')
depends=("linuxqq")
conflicts=("linuxqq-appimage" "liteloader-qqnt")
provides=("liteloader-qqnt")
source=("LiteLoaderQQNT-${pkgver}.zip::${url}/releases/download/${pkgver}/${_pkgname}.zip"
		"liteloader-qqnt-depatch.hook"
		"liteloader-qqnt-patch.hook")

sha256sums=('93c8520eb7cf26d2b8e06df70dc1c0d831734498dc9fd3767c099b4fbd89f5c0'
            '19c14e36baeffd1b385de2757cdaa8a68766ddea0480bbeec04efb7dcc2bc2d3'
            '4b0272c318e7ecc3ca941a9ecae9ae4085b78dace8e7d962d4b7d8c10b4aa1d5')

package() {
	# prepare to copy files
	mkdir -p "${pkgdir}/opt/LiteLoaderQQNT"
	# mkdir -p "${pkgdir}/opt/QQ/resources/app/application"

	# copy files
	cp -rf "${srcdir}"/* "${pkgdir}/opt/LiteLoaderQQNT/"
	# cp -f "${srcdir}/src/preload.js" "${pkgdir}/opt/QQ/resources/app/application/preload.js"

	# clean up in target dir
	rm -f "${pkgdir}/opt/LiteLoaderQQNT/LiteLoaderQQNT.zip"
	rm -f "${pkgdir}/opt/LiteLoaderQQNT/liteloader-qqnt-patch.hook"
	rm -f "${pkgdir}/opt/LiteLoaderQQNT/liteloader-qqnt-depatch.hook"

	# install hooks
	install -Dm644 "${srcdir}/liteloader-qqnt-patch.hook" "${pkgdir}/etc/pacman.d/hooks/liteloader-qqnt-patch.hook"
	install -Dm644 "${srcdir}/liteloader-qqnt-depatch.hook" "${pkgdir}/etc/pacman.d/hooks/liteloader-qqnt-depatch.hook"
}
