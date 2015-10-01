AC_INIT([Wt jumbo], [3.2.0], [koen@emweb.be])

AC_PREREQ([2.59])

have_libpng=yes
PKG_CHECK_MODULES([libpng], [libpng >= 1.2.0], [have_libpng=yes], [true]) 

have_libfreetype=no
AC_CHECK_LIB([freetype], [FT_Glyph_Copy], [have_libfreetype=yes], [true])

AC_PATH_PROG([wget], [wget], [no-wget], [/usr/bin:/usr/local/bin:/opt/local/bin])
AC_PATH_PROG([git], [git], [git], [/usr/bin:/usr/local/bin:/opt/local/bin])
AC_ARG_VAR([BOOST_PREFIX], [BOOST_PREFIX=<path_to_boost> e.g. /usr/local/boost_1_XX_Y])
AC_ARG_VAR([WT_CPP_11_MODE], [WT_CPP_11_MODE=-std=c++0  :  specify compiler mode])

AC_ARG_WITH([wt-version],
	[AS_HELP_STRING([--with-wt-version],
	  [Wt version (e.g. '3.2.3') or 'git'])],
	[],
	[with_wt_version=3.2.3])

AC_ARG_WITH([boost-version],
	[AS_HELP_STRING([--with-boost-version],
	  [Boost version (e.g. '1_59_0') ])],
	[],
	[with_boost_version=1_48_0])

AC_MSG_NOTICE([Setup for Wt version: $with_wt_version])

AC_SUBST(pkg_config, "$PKG_CONFIG")
AC_SUBST(system_libpng, $have_libpng)
AC_SUBST(system_libpng_ldflags, $libpng_LIBS)
AC_SUBST(system_libpng_cflags, $libpng_CFLAGS)
AC_SUBST(system_libfreetype, $have_libfreetype)
AC_SUBST(wget, $wget)
AC_SUBST(git, $git)
AC_SUBST(wt_version, $with_wt_version)
AC_SUBST(boost_version, $with_boost_version)
AC_CONFIG_FILES([Makefile])
AC_CONFIG_FILES([run-example])
AC_OUTPUT

chmod +x run-example
