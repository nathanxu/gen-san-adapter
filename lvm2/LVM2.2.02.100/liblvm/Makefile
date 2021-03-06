#
# Copyright (C) 2001-2004 Sistina Software, Inc. All rights reserved.
# Copyright (C) 2004-2013 Red Hat, Inc. All rights reserved.
#
# This file is part of LVM2.
#
# This copyrighted material is made available to anyone wishing to use,
# modify, copy, or redistribute it subject to the terms and conditions
# of the GNU General Public License v.2.
#
# You should have received a copy of the GNU General Public License
# along with this program; if not, write to the Free Software Foundation,
# Inc., 59 Temple Place, Suite 330, Boston, MA  02111-1307  USA

srcdir = .
top_srcdir = ..
top_builddir = ..

SOURCES =\
	lvm_misc.c \
	lvm_prop.c \
	lvm_base.c \
	lvm_lv.c \
	lvm_pv.c \
	lvm_vg.c

LIB_NAME = liblvm2app
LIB_VERSION = $(LIB_VERSION_APP)

ifeq ("no", "yes")
  LIB_STATIC = $(LIB_NAME).a
endif

LIB_SHARED = $(LIB_NAME).$(LIB_SUFFIX)

CLEAN_TARGETS += liblvm.cflow $(LIB_NAME).a

EXPORTED_HEADER = $(srcdir)/lvm2app.h
EXPORTED_FN_PREFIX = lvm

LDDEPS += $(top_builddir)/lib/liblvm-internal.a

include $(top_builddir)/make.tmpl

LIBS += $(LVMINTERNAL_LIBS) -ldevmapper

ifeq ("", "yes")
  LIBS += -ldevmapper-event
endif

.PHONY: install_dynamic install_static install_include install_pkgconfig

INSTALL_TYPE = install_dynamic

ifeq ("no", "yes")
  INSTALL_TYPE += install_static
endif

ifeq ("no", "yes")
  INSTALL_TYPE += install_pkgconfig
endif

install: $(INSTALL_TYPE) install_include

install_include: $(srcdir)/lvm2app.h
	$(INSTALL_DATA) -D $< $(includedir)/$(<F)

install_dynamic: install_lib_shared

install_static: $(LIB_STATIC)
	$(INSTALL_DATA) -D $< $(usrlibdir)/$(<F)

install_pkgconfig: $(LIB_NAME).pc
	$(INSTALL_DATA) -D $< $(pkgconfigdir)/lvm2app.pc

liblvm.cflow: $(SOURCES)
	set -e; (echo -n "SOURCES += "; \
		 echo $(SOURCES) | \
		 sed "s/^/ /;s/ / $(top_srcdir)\/liblvm\//g;s/$$//"; \
		 ) > $@

cflow: liblvm.cflow

DISTCLEAN_TARGETS += $(LIB_NAME).pc .exported_symbols_generated
