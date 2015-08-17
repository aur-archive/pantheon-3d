# Maintainer: Que Quotion <quequotion@bugmenot.org>
# Contributor: Maxime Gauduin <alucryd@archlinux.org>
# Contributor: Ner0 <darkelfdarkelf666@yahoo.co.uk>

pkgname=pantheon-3d
pkgver=1
pkgrel=2
pkgdesc='Pantheon 3d Session (pantheon/compiz desktop environment)'
arch=('i686' 'x86_64')
url='https://bbs.archlinux.org/viewtopic.php?pid=1401967#p1401967'
license=('GPL3')
depends=('dconf' 'compiz' 'pantheon-workarounds' 
         gnome-{settings-daemon{,-compat},session}
         {plank,cerbere,slingshot-launcher}-bzr)
[[ -n "$(pacman -Qq super-wingpanel-unstable-bzr 2>/dev/null)" ]] && \
  depends+=('super-wingpanel-unstable-bzr') || \
  depends+=('wingpanel-bzr')
optdepends=(indicator-{application,datetime,messages,printers,session,sound}-pantheon-bzr": Tray applet"
            "indicator-power-bzr: Tray applet"
            "network-manager-applet-ubuntu: Tray applet"
            "glippy-bzr: Simple, powerful clipboard manager"
            "indicator-powersave: On the fly power savings and performance toggles"
            "pantheon-notify-bzr: Popup notifications (freedesktop standard compliant)"
            "pantheon-print-bzr: Printer dialog (integrates with contractor-enabled applications)")
provides=("pantheon-3d")
conflicts=()
source=(pantheon-compiz.{desktop,session}
        compiz-qq.profile)
sha512sums=('18d3e1280c315014645e1f2ecf3bc5667e18fb718a83f46a6209b7d7b0fe407f69f23a567f67cddb0cb3dea8a8a99365529814d8093169b57ec308334bec10de'
            '8eda0a25ee90eabc7262e7f57d764457d651225ed841d5b1235b4792da5421132599e0b58eb41db7e8546a23791785c9a68f3b9860891d37ee5443daed4f17a3'
            '14da7533399fb1c1eb7ec6757aa6d6bc3ea452baa26df256c338bf64cb1fd142875b2f1c1db5afed8b362f7f009fecd37e7558e62ed78067d81748d0d2907bea')

package() {
  install -Dm655 {,"${pkgdir}"/usr/share/xsessions/}pantheon-compiz.desktop
  install -Dm655 {,"${pkgdir}"/usr/share/gnome-session/sessions/}pantheon-compiz.session
  # If you were prevously using compiz, check your configuration!
  #[[ -f "${HOME}"/.config/compiz-1/compizconfig/config ]] && \
  #  cp "${HOME}"/.config/compiz-1/compizconfig/config{,.bak}
  #[[ -n "$(cat "${HOME}"/.config/compiz-1/compizconfig/config | grep backend)" ]] && \
  #  sed -i 's|backend = ini|backend = gsettings|g' "${HOME}"/.config/compiz-1/compizconfig/config
}

