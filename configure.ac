AC_INIT([helloworld], [0.1], [ecidon@stanford.edu])

AS_CASE([$inptracemode],
	[lc], [INPTRACEMODEVAL=lc],
	[large-compiled], [INPTRACEMODEVAL=lc],
	[lm], [INPTRACEMODEVAL=lm],
	[large-manloaded], [INPTRACEMODEVAL=lm],
	[s], [INPTRACEMODEVAL=s],
	[small], [INPTRACEMODEVAL=s],
	[INPTRACEMODEVAL=s]
#	AC_MSG_ERROR([Unknown inptracemode flag value inptracemode=$inptracemode])
	)
AC_SUBST([INPTRACEMODEVAL])

AM_CONDITIONAL([INPTRACE_S], [test x$INPTRACEMODEVAL = xs])
AM_CONDITIONAL([INPTRACE_LC], [test x$INPTRACEMODEVAL = xlc])
AM_CONDITIONAL([INPTRACE_LM], [test x$INPTRACEMODEVAL = xlm])

AS_CASE([$samplesource],
	[eth], [SAMPLE_SOURCE=eth],
	[trace], [SAMPLE_SOURCE=trace],
	[SAMPLE_SOURCE=trace]
	)
AC_SUBST([SAMPLE_SOURCE])

AS_CASE([$snrber],
	[yes], [SNRBERDEFINED=yes],
	[no], [SNRBERDEFINED=no],
	[SNRBERDEFINED=no]
#	AC_MSG_ERROR([Unknown snrber flag value snrber=$snrber])
	)
AC_SUBST([SNRBERDEFINED])

AS_CASE([$debug],
	[4], [DEBUGLEVEL=4],
	[3], [DEBUGLEVEL=3],
	[2], [DEBUGLEVEL=2],
	[1], [DEBUGLEVEL=1],
	[0], [DEBUGLEVEL=0],
	[DEBUGLEVEL=0]
#	AC_MSG_ERROR([Unknown debug flag value debug=$debug])
	)
AC_SUBST([DEBUGLEVEL])

AS_CASE([$memconf],
	[memconf1], [MEMCONF=memconf1],
	[memconf2], [MEMCONF=memconf2],
	[memconf3], [MEMCONF=memconf3],
	[memconf4], [MEMCONF=memconf4],
	[memconf5], [MEMCONF=memconf5],
	[memconf6], [MEMCONF=memconf6],
	[memconf7], [MEMCONF=memconf7],
	[memconf8], [MEMCONF=memconf8],
	[memconf9], [MEMCONF=memconf9],
	[MEMCONF=memconf1]
#	AC_MSG_ERROR([Unknown memory configuration memconf=$memconf])
	)
AC_SUBST([MEMCONF])

AS_CASE([$tsconf],
	[st], [TIMESTAMPCONF=st],
	[at], [TIMESTAMPCONF=at],
	[atii], [TIMESTAMPCONF=atii],
	[none], [TIMESTAMPCONF=none],
	[TIMESTAMPCONF=none]
#	AC_MSG_ERROR([Unknown timestamp configuration tsconf=$tsconf])
	)
AC_SUBST([TIMESTAMPCONF])

AS_CASE([$host],

       [evm6474], [HOST=evm6474],
       [nyquist], [HOST=nyquist],
       [evm6670], [HOST=evm6670],
       [6638k2k], [HOST=6638k2k],
       [HOST=nyquist],
#       AC_MSG_ERROR([Unknown host platform --host=$host])
     )
AC_SUBST([HOST])

AM_CONDITIONAL([DEVICE_IS_6638K2K], [test x$HOST = x6638k2k])
#AM_INIT_AUTOMAKE([-Wall -Werror foreign subdir-objects])
#AM_INIT_AUTOMAKE([-Wall foreign subdir-objects])
AM_INIT_AUTOMAKE([-Wnone foreign subdir-objects])
AC_PROG_CC

AC_CHECK_PROG(REALPATH_CHECK,realpath,yes)
AC_CHECK_PROG(CYGPATH_CHECK,cygpath,yes)
if test x"$REALPATH_CHECK" != x"yes" -a x"$CYGPATH_CHECK" != x"yes" ; then
    AC_MSG_ERROR([Neither cygpath nor realpath exists on the current path. \
    If you are using cygwin, ensure the presence of cygpath. \
    If you are using a *nix shell, install realpath.])
fi

AC_SUBST([CYGPATH_W],["_cygpath -w"])
AC_PROG_RANLIB

AC_SUBST([CCS_ROOT_VAL],[${CCS_ROOT}])
AC_SUBST([ATOMIX_ROOT_VAL],[${ATOMIX_ROOT}])
AC_SUBST([ATOMIX_INSTALL_DIR_VAL],[${ATOMIX_INSTALL_DIR}])


AC_CONFIG_HEADERS([config.h])
AC_CONFIG_FILES([
 helloworld1/Makefile
 helloworld2/Makefile
 helloworld3/Makefile
 Makefile
])

AC_OUTPUT
