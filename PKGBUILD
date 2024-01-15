# Maintainer: Liam Timms <timms5000@gmail.com>
# Maintainer: Sin Kim <kimsin98@gmail.com>
# Maintainer: Caleb Maclennan <caleb@alerque.com>

_pkgname=datalad
pkgname=python-$_pkgname
pkgver=0.19.5
pkgrel=1
pkgdesc='Keep code, data, containers under control with git and git-annex'
arch=(any)
url='https://github.com/datalad/datalad'
license=(MIT)
depends=(git-annex
         patool
         python
         python-annexremote
         python-boto
         python-chardet
         python-distro
         python-fasteners
         python-gitlab
         python-humanize
         python-iso8601
         python-keyring
         python-keyrings-alt
         python-looseversion
         python-msgpack
         python-packaging
         python-platformdirs
         python-setuptools # used at runtime
         python-requests
         python-tqdm)
makedepends=(python-{build,installer,wheel})
checkdepends=(mypy
              python-beautifulsoup4
              python-httpretty
              python-pytest
              python-types-python-dateutil
              python-types-requests
              python-vcrpy)
optdepends=('python-requests-ftp: extra downloaders'
            'python-argcomplete: optional CLI completion'
            'python-pyperclip: clipboard manipulations'
            'python-dateutil: support for more date formats')
_archive="$_pkgname-$pkgver"
source=("$url/archive/$pkgver/$_archive.tar.gz")
sha256sums=('bb5cd9b520e7e7de5c42a6895cbafcd6f28b10fc7bbedcbc004546b6c75cc834')

build() {
	cd "$_archive"
	python -m build -wn
}

check() {
	cd "$_archive"
	pytest
}

package() {
	cd "$_archive"
	python -m installer -d "$pkgdir" dist/*.whl
	install -Dm0644 -t "$pkgdir/usr/share/licenses/$pkgname/" COPYING
}
