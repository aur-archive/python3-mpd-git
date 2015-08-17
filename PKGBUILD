# Contributor: stonecrest <stonecrest[at]gmail[dot]com>

pkgname=python3-mpd-git
pkgver=20120211
pkgrel=1
pkgdesc="Python3 MPD client library"
url="http://pypi.python.org/pypi/python-mpd/"
depends=('python')
license=('GPL3')
arch=('i686' 'x86_64')
conflicts=('python3-mpd')
provides=('python3-mpd')
source=()
md5sums=()
_gitroot="http://github.com/Mic92/python-mpd.git"
_gitname="python-mpd"

package() {
    cd $srcdir

    msg "Connecting to GIT server..."

    if [ -d $srcdir/$_gitname ] ; then
    cd $_gitname && git pull origin
    msg "The local files are updated."
    else
    git clone $_gitroot
    fi

    msg "GIT checkout done or server timeout"
    msg "Starting make..."

# Copy Latest files to Build Directory
    cp -r $srcdir/$_gitname $srcdir/$_gitname-build
    cd $srcdir/$_gitname-build

# Install
    python3 setup.py install --root="$pkgdir" || return 1

}
