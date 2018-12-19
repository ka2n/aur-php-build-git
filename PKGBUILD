# Maintainer: Márk Sági-Kazár <mark.sagi-kazar@gmail.com>

pkgname=php-build-git
pkgver=0.10.0.r599.g62dc493
pkgrel=1
pkgdesc="Install PHP versions"
arch=("any")
url="https://github.com/php-build/php-build"
license=("MIT")
depends=("libmcrypt" "gmp" "tidyhtml")
makedepends=("git")
provides=("${pkgname%-git}")
conflicts=("${pkgname%-git}")
source=("git://github.com/php-build/php-build")
md5sums=("SKIP")

pkgver() {
	cd "${srcdir}/${pkgname%-git}"

	git describe --long | sed 's/^v//;s/\([^-]*-g\)/r\1/;s/-/./g'
}

package() {
	cd "${srcdir}/${pkgname%-git}"

	mkdir -p "${pkgdir}/usr/share/licenses/${pkgname%-git}"
	install -Dm644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname%-git}/LICENSE"

	PREFIX="$pkgdir/usr" ./install.sh
}
