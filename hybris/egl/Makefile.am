SUBDIRS = platforms

lib_LTLIBRARIES = \
	libEGL.la

libEGL_la_SOURCES = \
	egl.c \
	ws.c

pkgconfigdir = $(libdir)/pkgconfig
pkgconfig_DATA = egl.pc

libEGL_la_CFLAGS = -I$(top_srcdir)/include -DPKGLIBDIR="\"$(pkglibdir)/\""
if WANT_MESA
libEGL_la_CFLAGS += -DLIBHYBRIS_WANTS_MESA_X11_HEADERS
endif
if WANT_TRACE
libEGL_la_CFLAGS += -DDEBUG
endif
if WANT_DEBUG
libEGL_la_CFLAGS += -ggdb -O0
endif

libEGL_la_CXXFLAGS = -I$(top_srcdir)/include -DPKGLIBDIR="\"$(pkglibdir)/\""
if WANT_MESA
libEGL_la_CXXFLAGS += -DLIBHYBRIS_WANTS_MESA_X11_HEADERS
endif
if WANT_TRACE
libEGL_la_CXXFLAGS += -DDEBUG
endif
if WANT_DEBUG
libEGL_la_CXXFLAGS += -ggdb -O0
endif
libEGL_la_LDFLAGS = \
	-ldl \
	$(top_builddir)/common/libhybris-common.la \
	$(top_builddir)/hardware/libhardware.la \
	-version-info "1":"0":"0"

eglincludedir = $(includedir)/EGL
eglinclude_HEADERS = \
	eglhybris.h
