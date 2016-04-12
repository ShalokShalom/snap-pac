pkgname=snap-pac
pkgver=0.2
pkgrel=1
pkgdesc="Make pacman automatically use snapper to create pre/post snapshots like openSUSE's YaST"
arch=('x86_64')
url="https://github.com/wesbarnett/snap-pac"
license=('LGPL')
depends=('snapper' 'grub-btrfs-git')
source=(${url}/archive/${pkgver}.tar.gz
        snap-pac.install)
install="snap-pac.install"
md5sums=('aba7420175d397349b092075aa299de9'
         'f278fda31aafe46b2e5e3354a819ca45')

package() {
    cd "$pkgname-$pkgver"
    install -d $pkgdir/usr/bin
    install -d $pkgdir/usr/share/libalpm/hooks
    install -D snapper-pac-pre $pkgdir/usr/bin/
    install -D snapper-pac-post $pkgdir/usr/bin/
    install -D snapper-pac-grub $pkgdir/usr/bin/
    install -D 10_snapper-pre.hook $pkgdir/usr/share/libalpm/hooks/
    install -D 10_snapper-post.hook $pkgdir/usr/share/libalpm/hooks/
    install -D 99_grub-config.hook $pkgdir/usr/share/libalpm/hooks/
    install -D LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}
