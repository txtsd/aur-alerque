# PKGBUILD generated by pipman
# Python package author: Kolen Cheung <christian.kolen@gmail.com>
pkgname=python-pantable
pkgver=0.11.1
pkgrel=1
pkgdesc="CSV Tables in Markdown: Pandoc Filter for CSV Tables"
arch=(any)
url="https://github.com/ickc/pantable"
license=(GPLv3)
makedepends=("python" "python-pip")
build() {
  pip install --no-deps --target="pantable" pantable==0.11.1
}
package() {
  sitepackages=$(python -c "import site; print(site.getsitepackages()[0])")
  mkdir -p $pkgdir/"$sitepackages"
  cp -r $srcdir/pantable/* $pkgdir/"$sitepackages"
}