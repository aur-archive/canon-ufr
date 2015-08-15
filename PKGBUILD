# Contributor: Allen Choong <allencch at hotmail dot com>

pkgname=canon-ufr
pkgver=2.70
pkgrel=2
pkgdesc="Canon UFR II/UFR II LT Printer Driver (including Canon imageCLASS MF4720w)"
url="http://support-asia.canon-asia.com/contents/ASIA/EN/0100270810.html"
arch=('i686' 'x86_64')
depends=('libxml2')
[ "$CARCH" = "x86_64" ] && depends=('lib32-libxml2')
license=('custom')
source=("Linux_UFRII_PrinterDriver_V270_uk_EN.tar.gz::http://pdisp01.c-wss.com/gdl/WWUFORedirectTarget.do?id=MDEwMDAwMjcwODA5")
md5sums=("56b71ad6f8011a735e0409128a79416f")


package() {
	if [ "${CARCH}" = 'x86_64' ]; then
	  dir=64-bit_Driver
	  suffix=amd64
	elif [ "${CARCH}" = 'i686' ]; then
	  dir=32-bit_Driver
	  suffix=i386
	fi
	cd "${srcdir}/Linux_UFRII_PrinterDriver_V270_uk_EN/${dir}/Debian/"
	ar xv cndrvcups-common_2.70-1_${suffix}.deb
	tar xzf data.tar.gz
	ar xv cndrvcups-ufr2-uk_2.70-1_${suffix}.deb
	tar xzf data.tar.gz
	mv usr etc ${pkgdir}
}
