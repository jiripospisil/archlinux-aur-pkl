# Maintainer: Jiri Pospisil <jiri@jpospisil.com>

pkgname=pkl
pkgver=0.26.0
pkgrel=1
pkgdesc='A configuration as code language with rich validation and tooling.'
arch=('x86_64')
url='https://pkl-lang.org'
license=('Apache')
depends=('glibc' 'zlib')
makedepends=('jdk-openjdk' 'git')
changelog=CHANGELOG
source=("https://github.com/apple/pkl/archive/refs/tags/$pkgver.tar.gz")
b2sums=('09503f27daf8b13978ce56bd93856a2b37e700926215ff5e7906ef4c39083746e68b0b88560d003ca3d86af968580d7d131033e229ba4e7217020b849adad3cd')

build() {
  cd "$srcdir/pkl-$pkgver"
  ./gradlew --info --stacktrace -DreleaseBuild=true pkl-cli:linuxExecutableAmd64
}

package() {
  cd "$srcdir/pkl-$pkgver"
  install -Dm755 "pkl-cli/build/executable/pkl-linux-amd64" "$pkgdir/usr/bin/pkl"
}
