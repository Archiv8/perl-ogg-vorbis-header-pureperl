#!/bin/bash

# Disable various shellcheck rules that produce false positives in this file.
# Repository rules should be added to the .shellcheckrc file located in the
# repository root directory, see https://github.com/koalaman/shellcheck/wiki
# and https://archiv8.github.io for further information.
# shellcheck disable=SC2034,SC2154
# ToDo: Add files: User documentation
# ToDo: Add files: Tooling
# FixMe: Namcap warnings and errors

# Maintainer: Ross Clark <https://github.com/Archiv8/perl-ogg-vorbis-header-pureperl/discussions>
# Contributor: Ross Clark <https://github.com/Archiv8/perl-ogg-vorbis-header-pureperl/discussions>

_relname="Ogg-Vorbis-Header-PurePerl"

pkgname="perl-ogg-vorbis-header-pureperl"
pkgver=1.05
pkgrel=1
pkgdesc="Perl/CPAN module Ogg::Vorbis::Header::PurePerl - An object-oriented interface to Ogg Vorbis info and comments"
arch=(
  "any"
)
license=(
  "GPL"
)
url="https://metacpan.org/release/DANIEL/Ogg-Vorbis-Header-PurePerl-1.05"
options=(
  !emptydirs
  purge
)
_tarname="${_relname}-${pkgver}"
source=(
  "http://cpan.metacpan.org/authors/id/D/DA/DAVECROSS/${_tarname}.tar.gz"
)
sha512sums=(
  "46d040ad8cd7d51187ca06b4d8968ad9009a8f4e2b5a164cb5318b8ec126adba787b0d70ace6feda810eaea37e63761dc25dbaa399d86c8fd1a13fe0fc07296f"
)

package() {

  cd "${srcdir}/${_tarname}"

  # install module in vendor directories.
  PERL_MM_USE_DEFAULT=1 perl Makefile.PL INSTALLDIRS=vendor || return 1

  make || return 1

  make install DESTDIR="${pkgdir}" || return 1
}
