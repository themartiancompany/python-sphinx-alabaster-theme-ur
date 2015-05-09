# Maintainer:
# Contributor: xantares

pkgbase=python-sphinx-alabaster-theme
pkgname=(python-sphinx-alabaster-theme python2-sphinx-alabaster-theme)
pkgver=0.7.4
pkgrel=1
arch=(any)
pkgdesc="Modified Kr Sphinx doc theme"
url='https://github.com/bitprophet/alabaster'
license=(BSD)
makedepends=(python-setuptools python2-setuptools)
source=("https://github.com/bitprophet/alabaster/archive/${pkgver}.tar.gz")
md5sums=('ed0f1f6cba60e930cba5ed45276b5323')

build() {
  cp -r ${srcdir}/alabaster-${pkgver} ${srcdir}/alabaster-${pkgver}-py2
  
  cd "$srcdir"/alabaster-${pkgver}
  python setup.py build

  cd "$srcdir"/alabaster-${pkgver}-py2
  python2 setup.py build
}

package_python-sphinx-alabaster-theme() {
  cd "$srcdir"/alabaster-${pkgver}
  python setup.py install --root="$pkgdir" --optimize=1

  install -Dm644 LICENSE "$pkgdir"/usr/share/licenses/$pkgname/LICENSE
}

package_python2-sphinx-alabaster-theme() {
  cd "$srcdir"/alabaster-${pkgver}-py2 
  python2 setup.py install --root="$pkgdir" --optimize=1

  install -Dm644 LICENSE "$pkgdir"/usr/share/licenses/$pkgname/LICENSE
}

