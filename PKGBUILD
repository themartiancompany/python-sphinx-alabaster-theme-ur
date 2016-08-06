# Maintainer: Johannes Löthberg <johannes@kyriasis.com>
# Contributor: xantares

pkgbase=python-sphinx-alabaster-theme
pkgname=(python-sphinx-alabaster-theme python2-sphinx-alabaster-theme)
pkgver=0.7.9
pkgrel=1

pkgdesc="Sphinx default theme"
url='https://github.com/bitprophet/alabaster'
arch=('any')
license=('custom:BSD')

makedepends=('python-setuptools' 'python2-setuptools')

source=("https://github.com/bitprophet/alabaster/archive/$pkgver.tar.gz")

md5sums=('efcded08511153c141385299a0121f5a')

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
