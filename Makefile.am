ACLOCAL_AMFLAGS = -I m4

lib_LTLIBRARIES = libstb-hal.la
libstb_hal_la_SOURCES =
SUBDIRS = common tools
bin_PROGRAMS = libstb-hal-test

libstb_hal_la_LIBADD = \
	common/libcommon.la

libstb_hal_la_LDFLAGS = -version-info 1:0:1

libstb_hal_test_SOURCES = libtest.cpp
libstb_hal_test_LDADD = libstb-hal.la

# there has to be a better way to do this...
if BOXTYPE_TRIPLE
SUBDIRS += libtriple
libstb_hal_la_LIBADD += \
	libtriple/libtriple.la
endif
if BOXTYPE_AZBOX
SUBDIRS += azbox
libstb_hal_la_LIBADD += \
	azbox/libazbox.la
endif
if BOXTYPE_GENERIC
if BOXMODEL_RASPI
SUBDIRS += raspi
libstb_hal_la_LIBADD += \
	raspi/libraspi.la
else
SUBDIRS += generic-pc
libstb_hal_la_LIBADD += \
	generic-pc/libgeneric.la
endif
endif
if BOXTYPE_SPARK
SUBDIRS += libspark libeplayer3
libstb_hal_la_LIBADD += \
	libspark/libspark.la \
	libeplayer3/libeplayer3.la
endif

pkginclude_HEADERS = \
	include/audio_hal.h \
	include/ca_cs.h \
	include/ca.h \
	include/cs_api.h \
	include/cs_types.h \
	include/dmx_cs.h \
	include/dmx_hal.h \
	include/glfb.h \
	include/hardware_caps.h \
	include/init_cs.h \
	include/init_td.h \
	include/mmi.h \
	include/playback.h \
	include/playback_hal.h \
	include/pwrmngr.h \
	include/record_hal.h \
	include/video_hal.h
