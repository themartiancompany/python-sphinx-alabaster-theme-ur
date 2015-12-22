# Maintainer: Johannes Löthberg <johannes@kyriasis.com>
# Contributor: xantares

pkgbase=python-sphinx-alabaster-theme
pkgname=(python-sphinx-alabaster-theme python2-sphinx-alabaster-theme)
pkgver=0.7.7
pkgrel=1

pkgdesc="Modified Kr Sphinx doc theme"
url='https://github.com/bitprophet/alabaster'
arch=(any)
license=(BSD)

makedepends=(python-setuptools python2-setuptools)

source=("https://github.com/bitprophet/alabaster/archive/$pkgver.tar.gz")

md5sums=('4151237e852bdd641ef51eaa8c9f33d9')

build() {
	cp -r alabaster-"$pkgver" alabaster-"$pkgver"-py2

	cd alabaster-"$pkgver"
	python setup.py build

	cd "$srcdir"/alabaster-"$pkgver"-py2
	python2 setup.py build
}

package_python-sphinx-alabaster-theme() {
	cd alabaster-"$pkgver"
	python setup.py install --root="$pkgdir" --optimize=1

	install -Dm644 LICENSE "$pkgdir"/usr/share/licenses/"$pkgname"/LICENSE
}

package_python2-sphinx-alabaster-theme() {
	cd alabaster-"$pkgver"-py2
	python2 setup.py install --root="$pkgdir" --optimize=1

	install -Dm644 LICENSE "$pkgdir"/usr/share/licenses/"$pkgname"/LICENSE
}
