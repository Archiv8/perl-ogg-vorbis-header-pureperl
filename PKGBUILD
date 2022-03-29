#!/bin/bash

# Disable various shellcheck rules that produce false positives in this file.
# Repository rules should be added to the .shellcheckrc file located in the
# repository root directory, see https://github.com/koalaman/shellcheck/wiki
# and https://archiv8.github.io for further information.
# shellcheck disable=SC2034,SC2154
# ToDo: Add files: User documentation
# ToDo: Add files: Tooling
# FixMe: Namcap warnings and errors

# Maintainer: Ross Clark <archiv8@artisteducator.com>
# Contributor: Ross Clark <archiv8@artisteducator.com>

pkgname=perl-ogg-vorbis-header-pureperl
pkgver=1.0
pkgrel=1
pkgdesc="Perl/CPAN module Ogg::Vorbis::Header::PurePerl - An object-oriented interface to Ogg Vorbis info and comments"
arch=(any)
license=(GPL)
url="http://search.cpan.org/~daniel/Ogg-Vorbis-Header-PurePerl-$pkgver/PurePerl.pm"
options=(!emptydirs purge)
source=(http://search.cpan.org/CPAN/authors/id/D/DA/DANIEL/Ogg-Vorbis-Header-PurePerl-$pkgver.tar.gz)
md5sums=('1b09cefefd4a83bd4a53d2fddbd0bc68')

package() {
  cd "${srcdir}/Ogg-Vorbis-Header-PurePerl-${pkgver}"

  # install module in vendor directories.
  PERL_MM_USE_DEFAULT=1 perl Makefile.PL INSTALLDIRS=vendor || return 1
  make  || return 1
  make install DESTDIR=${pkgdir} || return 1

}
