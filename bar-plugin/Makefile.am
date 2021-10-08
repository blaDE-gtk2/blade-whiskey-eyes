AM_CPPFLAGS = 										\
	-DGLIB_DISABLE_DEPRECATION_WARNINGS \
	-I$(top_srcdir)									\
	-DPACKAGE_LOCALE_DIR=\"$(localedir)\"			\
	-DTHEMESDIR=\"$(datadir)/xfce4/eyes/themes\"

plugindir = $(libdir)/xfce4/bar/plugins
plugin_LTLIBRARIES = libeyes.la

libeyes_la_SOURCES =					\
	eyes.h								\
	eyes.c								\
	themes.h							\
	themes.c

libeyes_la_CFLAGS =						\
	$(LIBBLADEUI_CFLAGS)				\
	$(LIBBLADEBAR_CFLAGS)

libeyes_la_LIBADD =						\
	$(LIBBLADEBAR_LIBS)				\
	$(LIBBLADEUI_LIBS)

libeyes_la_LDFLAGS =					\
	-avoid-version 						\
	-module 							\
	-no-undefined						\
	-export-symbols-regex '^blade_bar_module_(preinit|init|construct)' \
	$(PLATFORM_LDFLAGS)

desktopdir = $(datadir)/xfce4/bar/plugins
desktop_in_files = eyes.desktop.in
desktop_DATA = $(desktop_in_files:.desktop.in=.desktop)
@INTLTOOL_DESKTOP_RULE@

EXTRA_DIST = $(desktop_in_files)

CLEANFILES = $(desktop_DATA)

# vi:set ts=8 sw=8 noet ai nocindent syntax=automake:
