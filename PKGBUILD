# Maintainer: Christian Hesse <mail@eworm.de>

pkgname=yubico-pam
pkgver=2.19
pkgrel=1
pkgdesc='Yubico YubiKey PAM module'
arch=('i686' 'x86_64')
url='https://github.com/Yubico/yubico-pam'
license=('BSD')
depends=('pam' 'yubico-c-client' 'yubikey-personalization' 'json-c')
makedepends=('git')
checkdepends=('perl-net-ldap-server')
provides=('pam_yubico')
conflicts=('pam_yubico' 'yubico-pam-git')
source=("git://github.com/Yubico/yubico-pam.git#tag=${pkgver}")

build() {
	cd yubico-pam/

	autoreconf -fi
	./configure --prefix=/usr
	make
}

check() {
	cd yubico-pam/

	make check
}

package() {
	cd yubico-pam/

	install -D -m0644 COPYING "${pkgdir}/usr/share/licenses/yubico-pam/COPYING"
	install -D -m0644 README "${pkgdir}/usr/share/doc/yubico-pam/README"
	make DESTDIR="${pkgdir}/" install
}

sha256sums=('SKIP')
