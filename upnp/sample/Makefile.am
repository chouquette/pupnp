#
# "Makefile.am" for "libupnp/upnp/sample"
#
# Copyright (C) 2007 Marcelo Roberto Jimenez <mroberto@users.sourceforge.net>
#

AM_CPPFLAGS = \
	-I$(top_srcdir)/upnp/inc \
	-I$(top_srcdir)/threadutil/inc \
	-I$(top_srcdir)/ixml/inc

AM_CFLAGS = $(PTHREAD_CFLAGS)

AM_LDFLAGS = $(PTHREAD_LIBS)

LDADD = \
	$(top_builddir)/upnp/libupnp.la \
	$(top_builddir)/threadutil/libthreadutil.la \
	$(top_builddir)/ixml/libixml.la


# samples
noinst_PROGRAMS =
if ENABLE_SAMPLES
if ENABLE_CLIENT
noinst_PROGRAMS += upnp_tv_ctrlpt
upnp_tv_ctrlpt_CPPFLAGS = \
	$(AM_CPPFLAGS) \
	-I$(srcdir)/common/ \
	-I$(srcdir)/tvctrlpt
endif
if ENABLE_DEVICE
noinst_PROGRAMS += upnp_tv_device
upnp_tv_device_CPPFLAGS = \
	$(AM_CPPFLAGS) \
	-I$(srcdir)/common/ \
	-I$(srcdir)/tvdevice
endif
endif


upnp_tv_device_SOURCES = \
	common/sample_util.c \
	common/sample_util.h \
	tvdevice/upnp_tv_device.c \
	tvdevice/upnp_tv_device.h \
	tvdevice/linux/upnp_tv_device_main.c


upnp_tv_ctrlpt_SOURCES = \
	common/sample_util.c \
	common/sample_util.h \
	tvctrlpt/upnp_tv_ctrlpt.c \
	tvctrlpt/upnp_tv_ctrlpt.h \
	tvctrlpt/linux/upnp_tv_ctrlpt_main.c


if WITH_DOCUMENTATION
examplesdir = $(docdir)/examples
examples_DATA = \
		$(upnp_tv_ctrlpt_SOURCES) \
		$(upnp_tv_device_SOURCES)
endif


EXTRA_DIST = \
	tvdevice/web/tvcontrolSCPD.xml \
	tvdevice/web/tvdevicedesc.xml \
	tvdevice/web/tvdevicepres.html \
	tvdevice/web/tvpictureSCPD.xml
