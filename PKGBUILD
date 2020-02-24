# Maintainer: Caleb Maclennan <caleb@alerque.com>
# Mantainer: Michael M. Tung <mtung at mat dot upv dot es>
# PKGBUILD generated by pipman
# Python package author: Sergio Correia <sergio.correia@gmail.com>

_pipname=panflute
pkgname=python-$_pipname
pkgver=1.12.5
pkgrel=2
pkgdesc='A Pythonic alternative to John MacFarlane’s pandocfilters'
arch=('any')
url="https://github.com/sergiocorreia/$_pipname"
license=('BSD')
_pydeps=('click'
         'shutilwhich'
         'yaml')
depends=('python'  "${_pydeps[@]/#/python-}")
makedepends=('python-setuptools')
replaces=('pandoc-panflute')
source=("$pkgname-$pkgver.tar.gz::https://github.com/sergiocorreia/$_pipname/archive/$pkgver.tar.gz")
sha256sums=('ee62188825f7623eb348e15d2183c6ee51e28cf3f0c87c851e6f09ad7288f78d')

build() {
	cd "$_pipname-$pkgver"
	python setup.py build
}

package() {
    cd "$_pipname-$pkgver"
    python setup.py install --root="$pkgdir" --optimize=1 --skip-build
}
