# Adapted from original PKGBUILD by Harry Walker <me@harrywalker.uk>
pkgname=libfprint-focaltech
pkgver=0.1
pkgrel=1
pkgdesc="Proprietary driver for the Focaltech fingerprint reader"
arch=('x86_64')
url="https://github.com/ftfpteams/focaltech-linux-fingerprint-driver"
depends=('glib2>=2.56' 'libgusb>=0.3.0' 'nss>=3.13.4' 'pixman>=0.30.0')
conflicts=('libfprint')
provides=('libfprint-2.so' 'libfprint')
options=('!strip' '!emptydirs')
install=${pkgname}.install
source=("https://github.com/ftfpteams/focaltech-linux-fingerprint-driver/raw/refs/heads/main/Fedora_Redhat/libfprint-2-2_1.94.4+tod1_suse_all_x64_20250219.install")
sha512sums=('SKIP')

package(){
	# Extract package data
	sed "1,/^main \$@/d" libfprint-2-2_1.94.4+tod1_suse_all_x64_20250219.install > libfprint.tar.gz

	mkdir temp

	tar -x -f libfprint.tar.gz -C "temp"
	mkdir -p "${pkgdir}/usr/lib"

	mv temp/usr/lib64/libfprint-2.so.2.0.0 "${pkgdir}/usr/lib/."

	cd "${pkgdir}/usr/lib"

	ln -s libfprint-2.so.2.0.0 libfprint-2.so.2
	ln -s libfprint-2.so.2.0.0 libfprint-2.so
	
	chmod +x libfprint-2.so.2.0.0

	getent group plugdev > /dev/null || groupadd plugdev
}
