# Maintainer: Edoardo Maria Elidoro <edoardo.elidoro@gmail.com>
# Contributor: Jib <jbc.as (AT) free.fr>
# Last update: 01/26/11

pkgname=gtk-theme-bamboo-zen
_pkgname=bamboo-zen-theme
pkgver=1.5.1
pkgrel=2
pkgdesc="Bamboo-zen theme for Xfce and Mate."
arch=(any)
depends=('gtk-engine-murrine>=0.98')
optdepends=('slim-theme-bamboo-zen: matching theme for slim login manager')
install=bamboo-zen.install
license=('GPL')
source=(https://launchpad.net/~bisigi/+archive/ppa/+files/bamboo-zen-theme_1.5.1.maverick.ppa2.tar.gz
        arch-icon.svg
        bamboo-zen.patch)
url="http://www.bisigi-project.org"
md5sums=('d2fcd07fe021b1ea64b14eb01b87511a'
         '7e749ffb77988ddba93a460942cd7a59'
         '2f0c5531c4ba8c846d14356814e86371')

package() {
   cd ${srcdir}/${_pkgname}
   # install dirs 
   install -d ${pkgdir}/usr/share/{themes,icons,pixmaps/backgrounds/gnome/nature,gnome-background-properties,emerald/themes,doc/bisigi/bamboo-zen}

   tar -xzf Gtk/bamboo-zen.tar.gz -C Gtk/
   #Icons theme
   tar -xjf Icons/bamboo-zen.tar.bz2 -C Icons/
   install -D -m644 ${startdir}/arch-icon.svg Icons/Bamboo-zen/scalable/places/distributor-logo.svg
#*** check gnome-main-menu start-here = link
   #install -D -m644 ${startdir}/arch-icon.svg Icons/Bamboo-zen/scalable/places/gnome-main-menu.svg
   #install -D -m644 ${startdir}/arch-icon.svg Icons/Bamboo-zen/scalable/places/start-here.svg
   cd Icons/Bamboo-zen/scalable/actions
   ln -s system-shutdown-panel.svg system-shutdown.svg
   cd ../../../..
   # Emerald theme
   mkdir Emerald/bamboo-zen
   tar -xzf Emerald/bamboo-zen.emerald -C Emerald/bamboo-zen
   # install files
   patch -Np0 <${srcdir}/bamboo-zen.patch
   cp -R Gtk/bamboo-zen/ ${pkgdir}/usr/share/themes/
   cp -R Icons/Bamboo-zen/ ${pkgdir}/usr/share/icons
   install -D -m644 Wallpaper/Bamboo-Zen.jpg ${pkgdir}/usr/share/pixmaps/backgrounds/gnome/nature/
   install -D -m644 Wallpaper/bamboo-zen-wallpaper.xml ${pkgdir}/usr/share/gnome-background-properties
   cp -R Emerald/bamboo-zen ${pkgdir}/usr/share/emerald/themes/
   install -D -m644 credits.txt ${pkgdir}/usr/share/doc/bisigi/bamboo-zen/
}
