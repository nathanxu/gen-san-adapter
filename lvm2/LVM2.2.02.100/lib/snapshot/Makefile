#
# Copyright (C) 2002-2004 Sistina Software, Inc. All rights reserved.
# Copyright (C) 2004-2010 Red Hat, Inc. All rights reserved.
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

SOURCES = snapshot.c

LIB_SHARED = liblvm2snapshot.$(LIB_SUFFIX)
LIB_VERSION = $(LIB_VERSION_LVM)

include $(top_builddir)/make.tmpl

install: install_lvm2_plugin
