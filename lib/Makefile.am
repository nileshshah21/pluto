# Pluto
#
# Copyright (C) Uday Bondhugula 2007
#
SUBDIRS =

MAINTAINERCLEANFILES = Makefile.in

if EXTERNAL_ISL
# ISL_INCLUDE, ISL_LIBADD were already defined
else
ISL_INCLUDE += -I$(top_srcdir)/isl/include -I$(top_builddir)/isl/include
ISL_LIBADD += $(top_builddir)/isl/libisl.la
endif

lib_LTLIBRARIES = libpluto.la

# libpluto doesn't use polylib-based functions
libpluto_la_SOURCES = \
		      constraints.c \
		      constraints.h \
		      constraints_isl.c \
		      ddg.c \
		      ddg.h \
		      framework.cpp \
		      framework-dfp.c \
		      gurobi-plugin.c \
		      isl_support.c \
		      isl_support.h \
		      iss.c \
		      libpluto_dummy.c \
		      math_support.c \
		      math_support.h \
		      pluto.c \
		      plutolib.c \
		      pluto.h \
		      polyloop.c \
		      post_transform.c \
		      post_transform.h \
		      program.cpp \
		      program.h \
		      tile.c \
		      tile_size_selection_model.cpp \
		      transforms.c \
		      transforms.h \
					osl_pluto.h \
					osl_pluto.c \
					ast_transform.h \
		      ast_transform.c \
					pluto_codegen_if.h \
					pluto_codegen_if.c

libpluto_la_CXXFLAGS = $(OPT_FLAGS) $(DEBUG_FLAGS) \
   -DLIB_PLUTO -DSCOPLIB_INT_T_IS_LONGLONG -DCLOOG_INT_GMP \
   -I../include \
   -I$(top_srcdir)/include \
   -I../piplib/include \
   -I$(top_srcdir)/piplib/include \
	 -I../openscop/include \
	 -I$(top_srcdir)/openscop/include \
   -I../candl/include \
   -I$(top_srcdir)/candl/include \
   -I../cloog-isl/include \
   -I$(top_srcdir)/cloog-isl/include \
   $(ISL_INCLUDE)
# To avoid same name object from being created with libtool and without it.
libpluto_la_CFLAGS = $(AM_CFLAGS) $(libpluto_la_CXXFLAGS)

# libpluto doesn't use polylib
libpluto_la_LIBADD = \
   ../piplib/libpiplib_dp.la \
   $(ISL_LIBADD) \
   ../cloog-isl/libcloog-isl.la \
   ../candl/libcandl.la \
   -lm -lgomp
libpluto_la_LDFLAGS = -version-info 2:0:0
