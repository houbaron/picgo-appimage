# Maintainer: Baron Hou <houbaron@gmail.com>
latest_url=$(curl https://github.com/Molunerfinn/PicGo/releases/latest | cut -d '"' -f2)

pkgname=picgo-appimage
pkgver=$(echo $latest_url| cut -d 'v' -f2)

metadata=$(curl -L "https://github.com/Molunerfinn/PicGo/releases/download/v${pkgver}/latest-linux.yml")
# sha512=$(echo $metadata | grep '^sha512' |cut -d ' ' -f2)
sha512='e1d6bcc898ae3b42354c3c14c8146ef9d2f226a997bcde751b61b1495b0920c9534c76f49fd6e3d65e40280e086d033033c239a916b7cba1f5fb6ef037690f05'

pkgrel=1
pkgdesc="A simple & beautiful tool for pictures uploading built by electron-vue"
arch=('x86_64')
url="https://molunerfinn.com/PicGo/"
license=('MIT')
noextract=("PicGo-${pkgver}.AppImage")
options=("!strip")
source=(
    "https://github.com/Molunerfinn/PicGo/releases/download/v${pkgver}/PicGo-${pkgver}.AppImage"
    "picgo.png"
    "picgo.desktop"
)
sha512sums=(
    "${sha512}"
    'SKIP'
    'SKIP'
)

package() {
    install -Dm755 "PicGo-${pkgver}.AppImage" "${pkgdir}/opt/appimages/picgo.AppImage"
    install -Dm644 "picgo.desktop"                    "${pkgdir}/usr/share/applications/picgo.desktop"
    install -Dm644 "picgo.png"                        "${pkgdir}/usr/share/icons/hicolor/128x128/apps/picgo.png"
}
