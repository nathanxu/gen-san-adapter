# Copyright (C) 2011-2013 Red Hat, Inc. All rights reserved.
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
top_srcdir = ../..
top_builddir = ../..


UNITS = bitset_t.c matcher_t.c config_t.c string_t.c run.c

ifeq ($(MAKECMDGOALS),distclean)
SOURCES = $(UNITS)
endif

ifeq ("$(TESTING)", "yes")
SOURCES = $(UNITS)
TARGETS = run
endif

include $(top_builddir)/make.tmpl
ifeq ("$(TESTING)", "yes")
LDLIBS += -ldevmapper 
CFLAGS += 

check: unit

unit: $(TARGETS)
	@echo Running unit tests
	LD_LIBRARY_PATH=$(top_builddir)/libdm ./$(TARGETS)
endif
