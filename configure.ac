#                                               -*- Autoconf -*-
# Process this file with autoconf to produce a configure script.

AC_PREREQ([2.69])
AC_INIT([protoc-gen-php], [1.0], [github@bramp.net])
AC_CONFIG_SRCDIR([protoc-gen-php.cc])
AC_CONFIG_HEADERS([config.h])
AM_INIT_AUTOMAKE

# Checks for programs.
AC_PROG_CXX
AC_PROG_CC

AC_CHECK_PROG([PROTOC], [protoc], [protoc])
AS_IF([test "x${PROTOC}" == "x"],
    [AC_MSG_ERROR([Protobuf compiler "protoc" not found.])])

# Checks for libraries.
PKG_CHECK_MODULES(PROTOBUF, protobuf >= 2.6.1)
AC_SUBST(PROTOBUF_LIBS)
AC_SUBST(PROTOBUF_CFLAGS)
AC_SUBST(PROTOBUF_CFLAGS_ONLY_I)
AC_SUBST(PROTOBUF_VERSION)

# Checks for header files.
AC_CHECK_HEADERS([float.h limits.h stdlib.h])

# Checks for typedefs, structures, and compiler characteristics.
AC_CHECK_HEADER_STDBOOL
AC_C_INLINE
AC_TYPE_SIZE_T

# Checks for library functions.
AC_FUNC_STRTOD
AC_CHECK_FUNCS([localeconv memmove setlocale strchr strpbrk strtol strtoul strtoull])

AC_OUTPUT(Makefile)