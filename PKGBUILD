# Maintainer: Jiri Pospisil <jiri@jpospisil.com>

pkgname=pkl
pkgver=0.25.3
pkgrel=1
pkgdesc='A configuration as code language with rich validation and tooling.'
arch=('x86_64')
url='https://pkl-lang.org'
license=('Apache')
makedepends=('jdk-openjdk' 'git')
changelog=CHANGELOG
source=("https://github.com/apple/pkl/archive/refs/tags/$pkgver.tar.gz")
b2sums=('b9a005631315527315d77c79d0801aaba2c687e512a8c1c0dc9891fca48e0e353b4693bd82d44f10f16956d806015da89c86696c791cf3c5fd39c2ca5f3afe22')

build() {
  cd "$srcdir/pkl-$pkgver"
  ./gradlew --info --stacktrace -DreleaseBuild=true pkl-cli:linuxExecutableAmd64
}

package() {
  cd "$srcdir/pkl-$pkgver"
  install -Dm755 "pkl-cli/build/executable/pkl-linux-amd64" "$pkgdir/usr/bin/pkl"
}
