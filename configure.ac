dnl Process this file with autoconf to create configure.

AC_INIT
AC_CONFIG_SRCDIR([src/main.c])
AM_INIT_AUTOMAKE(scrot, 0.8)
AM_CONFIG_HEADER(src/config.h)

AC_PROG_CC
AM_PROG_CC_STDC
AC_C_CONST

AC_PROG_INSTALL
AC_PROG_MAKE_SET

AM_MAINTAINER_MODE

AC_PATH_GENERIC(giblib, 1.2.3, [
  AC_SUBST(GIBLIB_LIBS)
  AC_SUBST(GIBLIB_CFLAGS) ],
  AC_MSG_ERROR(Cannot find giblib: Is giblib-config in the path?) )

LIBS="$LIBS -lm"
GIBLIB_LIBS=`giblib-config --libs`
GIBLIB_CFLAGS=`giblib-config --cflags`
AC_SUBST(GIBLIB_LIBS)
AC_SUBST(GIBLIB_CFLAGS)

AC_CHECK_FUNC(getopt_long,,[LIBOBJS="$LIBOBJS getopt.o getopt1.o"])
AC_SUBST(LIBOBJS)

AC_CONFIG_FILES([Makefile \
scrot.spec \
src/Makefile \
])
AC_OUTPUT
