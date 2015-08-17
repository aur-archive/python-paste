#Maintainer: David Campbell <davekong@archlinux.us>
#Contributor: Cilyan Olowen <gaknar@gmail.com>
pkgname=python-paste
pkgver=1.7.5.1
pkgrel=1
pkgdesc="Tools for using a Web Server Gateway Interface stack."
arch=('any')
url="http://pythonpaste.org/index.html"
license=('custom')
depends=('python2')
makedepends=('setuptools')
source=(http://pypi.python.org/packages/source/P/Paste/Paste-${pkgver}.tar.gz)
optdepends=('python-flup: WSGI utilities'
            'python-openid: Support for OpenID')
md5sums=('7ea5fabed7dca48eb46dc613c4b6c4ed')

build() {
  cd ${srcdir}/Paste-${pkgver}
  python2 setup.py install --root=${pkgdir} --optimize=1
  install -Dm644 docs/license.txt ${pkgdir}/usr/share/licenses/$pkgname/license.txt
  sed -i -e "s|#![ ]*/usr/bin/python$|#!/usr/bin/python2|" \
         -e "s|#![ ]*/usr/bin/env python$|#!/usr/bin/env python2|" \
    $(find $pkgdir -name '*.py')
}
