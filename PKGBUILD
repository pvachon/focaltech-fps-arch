# Adapted from original PKGBUILD by Harry Walker <me@harrywalker.uk>
pkgname=libfprint-focaltech
pkgver=1.94.4
pkgrel=1
pkgdesc="Proprietary driver for the Focaltech fingerprint reader"
arch=('x86_64')
url="https://github.com/ftfpteams/focaltech-linux-fingerprint-driver"
depends=('glib2>=2.56' 'libgusb>=0.3.0' 'nss>=3.13.4' 'pixman>=0.30.0')
conflicts=('libfprint')
provides=('libfprint-2.so' 'libfprint')
options=('!strip' '!emptydirs')
license=('LicenseRef-Focaltech-Proprietary')
install=${pkgname}.install

sourcefile="libfprint-2-2_1.94.4+tod1_suse_all_x64_20250219.install"
source=("https://github.com/ftfpteams/focaltech-linux-fingerprint-driver/raw/refs/heads/main/Fedora_Redhat/${sourcefile}")
sha512sums=('4a4fa224fe3641e03cabe3a53da79f439671dd91c83b6b194256b915e985c055ade8f4e4226813f80614fdad6b1edff4477664984c5c996049b04cc8503a8d99')

package(){
	# Extract package data
	sed "1,/^main \$@/d" libfprint-2-2_1.94.4+tod1_suse_all_x64_20250219.install > libfprint-focaltech-${pkgver}.tar.gz

	mkdir libfprint-focaltech-${pkgver}

	tar -x -f libfprint-focaltech-${pkgver}.tar.gz -C "libfprint-focaltech-${pkgver}"
	mkdir -p "${pkgdir}/usr/lib"

	mv libfprint-focaltech-${pkgver}/usr/lib64/libfprint-2.so.2.0.0 "${pkgdir}/usr/lib/."

	pushd "${pkgdir}/usr/lib"

	ln -s libfprint-2.so.2.0.0 libfprint-2.so.2
	ln -s libfprint-2.so.2.0.0 libfprint-2.so

	chmod +x libfprint-2.so.2.0.0

    popd

    rm -rf libfprint-focaltech-${pkgver}
    rm -f libfprint-focaltech-${pkgver}.tar.gz
}

