#
# Copyright (c) 2014-2015 Intel, Inc.  All rights reserved.
# Copyright (c) 2015      Cisco Systems, Inc.  All rights reserved.
# Copyright (c) 2015      Research Organization for Information Science
#                         and Technology (RIST). All rights reserved.
# $COPYRIGHT$
#
# Additional copyrights may follow
#
# $HEADER$
#

EXTRA_DIST = autogen.subdirs

SUBDIRS = pmix

sources = \
        pmix1.h \
        pmix_pmix1_component.c \
        pmix_pmix1.c \
        pmix1_client.c \
        pmix1_server_south.c \
        pmix1_server_north.c

# Make the output library in this directory, and name it either
# mca_<type>_<name>.la (for DSO builds) or libmca_<type>_<name>.la
# (for static builds).

if MCA_BUILD_opal_pmix_pmix1xx_DSO
component_noinst =
component_install = mca_pmix_pmix1xx.la
else
component_noinst = libmca_pmix_pmix1xx.la
component_install =
endif

mcacomponentdir = $(opallibdir)
mcacomponent_LTLIBRARIES = $(component_install)
mca_pmix_pmix1xx_la_SOURCES = $(sources)
mca_pmix_pmix1xx_la_CFLAGS = $(opal_pmix_pmix1xx_CFLAGS)
mca_pmix_pmix1xx_la_CPPFLAGS = \
        -I$(srcdir)/pmix/include $(opal_pmix_pmix1xx_CPPFLAGS)
mca_pmix_pmix1xx_la_LDFLAGS = -module -avoid-version $(opal_pmix_pmix1xx_LDFLAGS)
mca_pmix_pmix1xx_la_LIBADD = $(opal_pmix_pmix1xx_LIBS)

noinst_LTLIBRARIES = $(component_noinst)
libmca_pmix_pmix1xx_la_SOURCES =$(sources)
libmca_pmix_pmix1xx_la_CFLAGS = $(opal_pmix_pmix1xx_CFLAGS)
libmca_pmix_pmix1xx_la_CPPFLAGS = -I$(srcdir)/pmix/include $(opal_pmix_pmix1xx_CPPFLAGS)
libmca_pmix_pmix1xx_la_LDFLAGS = -module -avoid-version $(opal_pmix_pmix1xx_LDFLAGS)
libmca_pmix_pmix1xx_la_LIBADD = $(opal_pmix_pmix1xx_LIBS)
