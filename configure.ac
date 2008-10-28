AC_INIT(gtassm, 0.1, http://gtasmm.org/)
AC_CONFIG_SRCDIR(src/main.c)
AM_INIT_AUTOMAKE(AC_PACKAGE_NAME, AC_PACKAGE_VERSION)
AM_CONFIG_HEADER(src/config.h)
AM_MAINTAINER_MODE

SQLITE_REQUIRED=3.0

AC_ISC_POSIX
AC_PROG_CC
AM_PROG_CC_STDC
AC_HEADER_STDC
AM_PROG_LIBTOOL

CFLAGS="-g -O0"

if test "x${prefix}" = "xNONE"; then
  prefix=${ac_default_prefix}
else
  prefix=${prefix}
fi

Z_DEFAULT_PREFIX="\${prefix}/etc"
if test "x${sysconfdir}" = "x${Z_DEFAULT_PREFIX}"; then
  sysconfdir=${prefix}/etc
else
  sysconfdir=${sysconfdir}
fi

development=""
develPWD=""
AC_MSG_CHECKING(for development flags)
AC_ARG_ENABLE(development,
        [  --enable-development    Do include development code like debugging messages ],
        [if test x"$enableval" = x"yes"
         then
                development="-DDEVEL=1"
                develPWD=`pwd`
         fi],
        development=""
)
if test -z "${development}"
then
        AC_MSG_RESULT(none)
else
        AC_MSG_RESULT(${development})
        AC_MSG_RESULT(${develPWD})
fi

GLOBAL_DEFINES="${development}"
DEVELPWD="${develPWD}"
AC_SUBST(GLOBAL_DEFINES)
AC_SUBST(DEVELPWD)

PREFIX=${prefix}
AC_SUBST(PREFIX)

ZEMBLA_SYSCONFDIR=${sysconfdir}
AC_MSG_RESULT(sysconfdir = ${GTASM_SYSCONFDIR})

# Check for iksemel library.
PKG_CHECK_MODULES( GTASSM,
        sqlite3 >= $SQLITE_REQUIRED
)

AC_SUBST(GTASSM_CFLAGS)
AC_SUBST(GTASSM_LIBS)
AC_SUBST(GTASSM_SYSCONFDIR)

AC_OUTPUT([
Makefile
src/Makefile
])
