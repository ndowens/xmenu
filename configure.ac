#                                               -*- Autoconf -*-
# Process this file with autoconf to produce a configure script.

AC_PREREQ([2.69])
AC_INIT([xmenu], [4.4.1], [https://github.com/phillbush/xmenu/issues])
AC_CONFIG_SRCDIR([config.h])
AC_CONFIG_HEADERS([config.h])

# Checks for programs.
AC_PROG_CC

AC_PATH_X
AC_CHECK_HEADERS([ftconfig.h])

LIBS=
AC_SEARCH_LIBS([FcInit], [fontconfig],
		[
			FONTCONFIG_LIBS="$LIBS"
			LIBS="$save_LIBS"],
				[AC_MSG_ERROR([Unable to find fontconfig])])

LIBS=
AC_SEARCH_LIBS([Xft],
		[xft],
		[
			Xft_LIBS="$LIBS"
			LIBS="$save_LIBS"
		],
			[AC_MSG_ERROR([Unable to find Xft])]
)

LIBS=
AC_SEARCH_LIBS([X11], [X11],
		[
			X11_LIBS="$LIBS"
			LIBS="$save_LIBS"
		],
			[AC_MSG_ERROR([Unable to find X11])]
)

LIBS=
AC_SEARCH_LIBS([Xinerama], [Xinerama],
		[
			Xinerama_LIBS="$LIBS"
			LIBS="$save_LIBS"
		],
			[AC_MSG_ERROR([Unable to find Xinerama])]
)

LIBS=
AC_SEARCH_LIBS([Imlib2], [Imlib2],
		[
			Imlib2_LIBS="$LIBS"
			LIBS="$save_LIBS"
		],
			[AC_MSG_ERROR([Unable to find X11])]
)

CFLAGS="$CFLAGS -I$(PREFIX)/include -I$(PREFIX)/include/freetype2"
LDFLAGS="$save_LIBS"

PREFIX=/usr
AC_ARG_WITH(PREFIX,
						[AS_HELP_STRING([--prefix], [Specify prefix path])])
AC_SUBST(PREFIX)

MANDIR=/usr/share/man
AC_ARG_WITH(MANDIR,
						[AS_HELP_STRING([--mandir], [Man dir location])])
AC_SUBST(MANDIR)

X11INC=/usr/X11R6/include
AC_ARG_WITH(X11INC,
						[AS_HELP_STRING([--x11inc-path=], [X11 header path])])
AC_SUBST(X11INC)

X11LIB=/usr/X11R6/lib
AC_ARG_WITH(X11LIB,
						[AS_HELP_STRING([--x11lib-path], [X11 library path])])
AC_SUBST(X11LIB)

FREETYPE=/usr/include/freetype2
AC_ARG_WITH(FREETYPE,
						[AS_HELP_STRING([--freetype-path], [Freetype header location])])
AC_SUBST(FREETYPE)


AC_CONFIG_FILES([Makefile.in])
AC_OUTPUT
