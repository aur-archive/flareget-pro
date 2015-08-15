# Author: Syed Adnan Kamili <adnan.kamili@gmail.com>
# Maintainer: Marc Rozanc <marc@rozanc.fr>

pkgbase=flareget
pkgname=${pkgbase}-pro
_rel=1.5
_subrel=12
pkgver=${_rel}.${_subrel}
pkgrel=2
pkgdesc="A full featured, advanced, multi-threaded, multisegment download manager and accelerator (pro version)"
arch=('i686' 'x86_64')
url="http://flareget.com"
license=('custom')
depends=('glibc>=2.13' 'qt4>=4.8.1' 'libpcap>=0.9.8')
makedepends=('rpmextract')
optdepends=('flaremonitor')
conflicts=($pkgbase)
provides=("${pkgbase}=$pkgver")
install=${pkgname}.install

if [ "${CARCH}" = "x86_64" ]; then 
    source=("${pkgbase}-${_rel}-${_subrel}.x86_64.rpm")
    md5sums=('83fa29f549a44df2bdcadf1da49c2322')
elif  [ "${CARCH}" = "i686" ]; then
    source=("${pkgbase}-${_rel}-${_subrel}.i386.rpm")
    md5sums=('983a328f3571df6d349974393bd54ea8')
fi

package() {
   cd $pkgdir

   # Extract .rpm package
   rpmextract.sh $srcdir/${source[0]}

   cd $srcdir
   # License
   install -Dm644 $pkgdir/usr/share/doc/$pkgbase/COPYING $pkgdir/usr/share/licenses/$pkgbase/LICENSE

   rm $pkgdir/usr/share/doc/$pkgbase/COPYING
}

