# Maintainer: James Bulmer <nekinie@gmail.com>

pkgname="neutron-deb"
pkgver=2014.1
pkgrel=1
pkgdesc="Openstack network"
arch=("i686" "x86_64")
url="http://docs.openstack.org/developer/neutron/"
license=("Apache")
groups=("openstack-deb")

depends=(
  "python2"
  "python2-paste"
  "python2-paste-deploy"
  "python2-routes"
  "python2-amqplib"
  "python2-anyjson"
  "python2-babel"
  "python2-eventlet"
  "python2-greenlet"
  "python2-httplib2"
  "python2-requests"
  "python2-iso8601"
  "python2-jsonrpclib"
  "python2-jinja"
  "python2-kombu"
  "python2-netaddr"
  "python2-neutronclient"
  "python2-sqlalchemy"
  "python2-webob"
  "python2-keystoneclient"
  "python2-alembic"
  "python2-six"
  "python2-stevedore"
  "python2-oslo-config"
  "python2-oslo-rootwrap"
  "python2-novaclient"
)

makedepends=("python2-setuptools")

conflicts=(
  "neutron",
  "openstack-neutron-git"
)

source=("http://archive.ubuntu.com/ubuntu/pool/main/n/neutron/neutron_${pkgver}.orig.tar.gz")
md5sums=("7e44f77c8d4704534724b34770e3224f")

build() {
  cd "${srcdir}/neutron-${pkgver}/"
  python2 setup.py build
}

package() {
  cd "${srcdir}/neutron-${pkgver}/"
  python2 setup.py install --root="${pkgdir}/" --optimize=1
  mv "${pkgdir}/usr/etc/" "${pkgdir}/etc/"
  rm -r "${pkgdir}/etc/init.d/"
}