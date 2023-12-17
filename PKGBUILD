pkgname=com.163.music.spark
pkgver=3.0.1.201795spark10
pkgrel=1
pkgdesc="Netease Music Wine Client from Spark Store"
url="https://music.163.com/"
arch=('x86_64')
depends=(
    'bash'
    'hicolor-icon-theme'
    'lib32-glibc'
    'lib32-libx11'
    'lib32-libxext'
    'spark-dwine-helper'
    'wine'
    'xdg-utils'
)
optdepends=(
    'wqy-microhei: recommended font'
    'wqy-zenhei: recommended font'
)
_mirror="https://mirrors.sdu.edu.cn/spark-store-repository"
source=("${_mirror}/store/music/${pkgname}/${pkgname}_${pkgver}_amd64.deb")
md5sums=('1fc6104eb494e1df3b4cdd95e6863baa')

package() {
    cd "${pkgdir}"
    bsdtar -xpvf "${srcdir}/data.tar.xz"
    install -d usr/share
    mv opt/apps/${pkgname}/entries/* usr/share
    sed -i 's/"spark-wine"/"wine"/' opt/apps/${pkgname}/files/run.sh
    rmdir opt/apps/${pkgname}/entries/
    rm opt/apps/${pkgname}/info
    chown -R root:root .
}