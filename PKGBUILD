# Contributor: dickeny@gmail.com
# Maintainer:  cuihao <cuihao dot leo at gmail dot com>

pkgname=man-pages-zh_cn
_pkgname=manpages-zh
pkgver=1.5.2
pkgrel=2
pkgdesc='Simplified Chinese Linux man pages'
arch=('any')
url=('https://github.com/lidaobing/manpages-zh')
license=('GPL2')
depends=('man-db')
conflicts=('man-pages-zh', 'manpages-zh')
source=("https://github.com/downloads/lidaobing/${_pkgname}/${_pkgname}-${pkgver}.tar.bz2")
md5sums=('cab232c7bb49b214c2f7ee44f7f35900')

build() {
    cd "${srcdir}/${_pkgname}-${pkgver}"
    ./configure --prefix=/usr --disable-zhtw
    make
}

package() {
    cd "${srcdir}/${_pkgname}-${pkgver}"
    make install DESTDIR="${pkgdir}"
    # 以下文件与软件包shadow冲突，故从本包删除。
    cd ${pkgdir}/usr/share/man/zh_CN
    rm -f \
        ./man1/chfn* \
        ./man1/chsh* \
        ./man1/groups* \
        ./man1/newgrp* \
        ./man5/passwd* \
        ./man8/chpasswd* \
        ./man8/groupadd* \
        ./man8/groupdel* \
        ./man8/groupmod* \
        ./man8/useradd* \
        ./man8/userdel* \
        ./man8/usermod*
}

