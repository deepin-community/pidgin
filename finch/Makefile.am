EXTRA_DIST = \
		getopt.c \
		getopt.h \
		getopt1.c \
		finch.pc.in

pkgconfigdir = $(libdir)/pkgconfig
pkgconfig_DATA = finch.pc

SUBDIRS = plugins

if ENABLE_GNT

bin_PROGRAMS = finch

endif

finch_SOURCES = \
	gntaccount.c \
	gntblist.c \
	gntcertmgr.c \
	gntconn.c \
	gntconv.c \
	gntdebug.c \
	gntft.c \
	finch.c \
	gntidle.c \
	gntlog.c \
	gntmedia.c \
	gntnotify.c \
	gntplugin.c \
	gntpounce.c \
	gntprefs.c \
	gntrequest.c \
	gntroomlist.c \
	gntsound.c \
	gntstatus.c \
	gntui.c

finch_headers = \
	gntaccount.h \
	gntblist.h \
	gntcertmgr.h \
	gntconn.h \
	gntconv.h \
	gntdebug.h \
	gntft.h \
	finch.h \
	gntidle.h \
	gntlog.h \
	gntmedia.h \
	gntnotify.h \
	gntplugin.h \
	gntpounce.h \
	gntprefs.h \
	gntrequest.h \
	gntroomlist.h \
	gntsound.h \
	gntstatus.h \
	gntui.h

finchincludedir=$(includedir)/finch
finchinclude_HEADERS = \
	$(finch_headers)

finch_DEPENDENCIES = @LIBOBJS@
finch_LDFLAGS = -export-dynamic
finch_LDADD = \
	@LIBOBJS@ \
	$(DBUS_LIBS) \
	$(INTLLIBS) \
	$(GLIB_LIBS) \
	$(LIBXML_LIBS) \
	$(GNT_LIBS) \
	$(GSTREAMER_LIBS) \
	$(GSTVIDEO_LIBS) \
	$(LIBGNT_LIBS) \
	$(top_builddir)/libpurple/libpurple.la

AM_CPPFLAGS = \
	-DSTANDALONE \
	-DGNTSEAL_ENABLE \
	-DDATADIR=\"$(datadir)\" \
	-DLIBDIR=\"$(libdir)/finch/\" \
	-DLOCALEDIR=\"$(datadir)/locale\" \
	-DSYSCONFDIR=\"$(sysconfdir)\" \
	-I$(top_srcdir)/libpurple/ \
	-I$(top_srcdir) \
	$(LIBGNT_CFLAGS) \
	$(DEBUG_CFLAGS) \
	$(GLIB_CFLAGS) \
	$(DBUS_CFLAGS) \
	$(LIBXML_CFLAGS) \
	$(GSTREAMER_CFLAGS) \
	$(GNT_CFLAGS)
