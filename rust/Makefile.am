# libguestfs rust bindings
# Copyright (C) 2019 Hiroyuki Katsura <hiroyuki.katsura.0513@gmail.com>
#
# This program is free software; you can redistribute it and/or modify
# it under the terms of the GNU General Public License as published by
# the Free Software Foundation; either version 2 of the License, or
# (at your option) any later version.
#
# This program is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU General Public License for more details.
#
# You should have received a copy of the GNU General Public License
# along with this program; if not, write to the Free Software
# Foundation, Inc., 51 Franklin Street, Fifth Floor, Boston, MA 02110-1301 USA.

include $(top_srcdir)/subdir-rules.mk

generator_built = \
	src/bin/bindtests.rs \
	src/guestfs.rs

EXTRA_DIST = \
	$(generator_built) \
	tests/*.rs \
	src/*.rs \
	src/bin/*.rs \
	README.md \
	run-bindtests \
	run-tests

if HAVE_RUST

all: $(srcdir)/src/lib.rs
	$(top_builddir)/run $(CARGO) build --release

distclean-local:
	$(top_builddir)/run $(CARGO) clean

TESTS = run-bindtests run-tests

CLEANFILES += target/*~

endif

TESTS_ENVIRONMENT = $(top_builddir)/run --test
