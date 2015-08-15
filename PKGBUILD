# Maintainer: rich_o <rich_o@lavabit.com>
# Contributor: Bram Schoenmakers <me@bramschoenmakers.nl>

pkgname="git-vim"
# There are no releases, only a git repository
pkgver=77.19b88ad
pkgrel=1
pkgdesc="Provides Git plugins for Vim and syntax files for Git displays."
arch=('any')
url="http://github.com/motemen/git-vim/"
license=('MIT')
depends=('vim' 'git')
makedepends=('git')
source=("git+git://github.com/motemen/${pkgname}.git")
md5sums=('SKIP')

pkgver() {
  cd "${SRCDEST}/${pkgname}"
  echo $(git rev-list --count HEAD).$(git rev-parse --short HEAD)
}

package() {
  cd "${srcdir}/${pkgname}"
  install -D -m 644 plugin/git.vim $pkgdir/usr/share/vim/vimfiles/plugin/git.vim
  install -d -m 755 $pkgdir/usr/share/vim/vimfiles/syntax/
  install -D -m 644 -t $pkgdir/usr/share/vim/vimfiles/syntax/ syntax/git-{diff,log,status}.vim
  find "${pkgdir}" -type d -name .git -exec rm -r '{}' +
}
# vim:syntax=sh
