#
# Copyright (C) 2010-2011 Red Hat, Inc. All rights reserved.
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
top_srcdir = ../../../..
top_builddir = ../../../..

CLDFLAGS += -L$(top_builddir)/tools

SOURCES = dmeventd_lvm.c

LIB_SHARED = libdevmapper-event-lvm2.$(LIB_SUFFIX)
LIB_VERSION = $(LIB_VERSION_LVM)

include $(top_builddir)/make.tmpl

LIBS +=  -ldevmapper $(PTHREAD_LIBS) $(DAEMON_LIBS)

install_lvm2: install_lib_shared

install: install_lvm2
