pkgname=RALUS
pkgver=14.0.1798.0
pkgrel=1
pkgdesc="Backup Exec Remote Agent for Linux and UNIX Servers"
url="http://www.symantec.com/"
license=('commercial')
arch=('i686' 'x86_64')
options=('!strip')
depends=('libstdc++5')
makedepends=('rpmextract' 'binutils')
source=(ralus.install
	ralus.service
	VRTSralus-14.0.1798-0.x86_64.rpm
)
install=ralus.install

md5sums=('265271924bc7a708e1fd39adf406cbb4'
         '5f56f9d5d14943cf4c57f060f179cf86'
         'e29f6dd301c5fae7bbe32a6477c756ee')

build() {

        # Extract RPM
	cd "${srcdir}"
	mkdir unpack
	cd unpack
        rpmextract.sh ../VRTSralus-14.0.1798-0.x86_64.rpm
	mkdir -p etc/systemd/system/
	cp ../ralus.service etc/systemd/system/

	# Kernel 3.x patch
	echo -n "Patching binary for 3.x kernel compatibility..."
	cd opt/VRTSralus/bin/
	pos=`objdump -D libbesocket.so | grep -6 0x8938 | grep '\.*:\?[[:space:]]\+79' | awk '{print $1}' | cut -d: -f1`
	echo -n "Found offset ${pos}..."
	echo "$pos: 78" | xxd -r - libbesocket.so
	echo "Done"
}

package() {
	cd "${srcdir}/unpack"
	cp -Rv * "${pkgdir}"
}
