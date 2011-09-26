lib_LIBRARIES = libSingular.a libSingular_g.a

all: libSingular.a libSingular_g.a Singular Singularg

# ACLOCAL_AMFLAGS = -I m4

# PIPE = -pipe
# ???
#LD_DYN_FLAGS	= -ldl -rdynamic
#SFLAGS		= -fpic -DPIC
#SLDFLAGS	= -shared
#LD_LIBC	        = -lc
#STATIC_LDFLAGS	= -static


NODEBUGCFLAGS   = -O3 -w -fomit-frame-pointer
NODEBUGCXXFLAGS = -O3 -w -fomit-frame-pointer --no-rtti 
NODEBUGDEFS = -DNDEBUG -DOM_NDEBUG 




CXXTEMPLFLAGS = --no-exceptions ## -fno-implicit-templates



INCLUDES = -I${top_srcdir} -I${top_builddir} -I${top_srcdir}/numeric -I${top_builddir}/numeric -I${top_srcdir}/kernel -I${top_builddir}/kernel -I${top_srcdir}/libpolys -I${top_builddir}/libpolys $(GMP_CFLAGS) $(FACTORY_CFLAGS) $(NTL_CFLAGS)
AM_CPPFLAGS	= -DHAVE_CONFIG_H

########################### liSingular* #########################

libSingular_a_CFLAGS   = -O3 -fomit-frame-pointer -Wextra -Wall -Wno-long-long ${PIPE}
libSingular_g_a_CFLAGS = -g -Wextra -Wall -Wno-long-long -pedantic ${PIPE}
## -pedantic

libSingular_a_CXXFLAGS   = -O3 -fomit-frame-pointer --no-rtti -Wextra -Wall -Wno-long-long ${PIPE} $(CXXTEMPLFLAGS)
libSingular_g_a_CXXFLAGS = -g -Wextra -Wall -Wno-long-long -pedantic ${PIPE} $(CXXTEMPLFLAGS)
# -fdiagnostics-show-option 

libSingular_a_CPPFLAGS   = -DNDEBUG -DOM_NDEBUG -DLIBSINGULAR
libSingular_g_a_CPPFLAGS = -DLIBSINGULAR

SOURCES =    Minor.cc\
   MinorInterface.cc\
   MinorProcessor.cc\
   attrib.cc\
   bbcone.cc\
   bbfan.cc\
   bigintm.cc\
   blackbox.cc\
   calcSVD.cc\
   cntrlc.cc\
   denom_list.cc\
   eigenval_ip.cc\
   extra.cc\
   feOpt.cc\
   fehelp.cc\
   fevoices.cc\
   fglm.cc\
   gms.cc\
   grammar.cc\
   interpolation.cc\
   iparith.cc\
   ipassign.cc\
   ipconv.cc\
   ipid.cc\
   iplib.cc\
   ipprint.cc\
   ipshell.cc\
   janet.cc\
   libparse.cc\
   linearAlgebra_ip.cc\
   lists.cc\
   maps_ip.cc\
   minpoly.cc\
   misc_ip.cc\
   mpsr_Error.cc\
   mpsr_Get.cc\
   mpsr_GetMisc.cc\
   mpsr_GetPoly.cc\
   mpsr_Put.cc\
   mpsr_PutPoly.cc\
   mpsr_Timer.cc\
   mpsr_Tok.cc\
   mpsr_sl.cc\
   ndbm.cc\
   newstruct.cc\
   pcv.cc\
   pipeLink.cc\
   scanner.cc\
   sdb.cc\
   silink.cc\
   sing_dbm.cc\
   sing_win.cc\
   slInit_Dynamic.cc\
   slInit_Static.cc\
   ssiLink.cc\
   subexpr.cc\
   utils.cc\
   walk.cc\
   walk_ip.cc\
   wrapper.cc\
   fereadl.c mmstd.c claptmpl.cc feOpt.h
   
#   tesths.cc


libSingular_a_SOURCES   = $(SOURCES)
libSingular_g_a_SOURCES = $(SOURCES)

libSingular_a_includedir  =${includedir}/Singular/
libSingular_g_a_includedir=${includedir}/Singular/

SingularHEADERS =    Cache.h \
   CacheImplementation.h \
   Minor.h \
   MinorInterface.h \
   MinorProcessor.h \
   attrib.h \
   bbcone.h \
   bigintm.h \
   blackbox.h \
   cntrlc.h \
   dbm_sl.h \
   distrib.h \
   eigenval_ip.h \
   feOpt.h \
   fglm.h \
   gms.h \
   grammar.h \
   interpolation.h \
   ipconv.h \
   ipid.h \
   ipprint.h \
   ipshell.h \
   janet.h \
   libparse.h \
   libsingular.h \
   lists.h \
   locals.h \
   maps_ip.h \
   minpoly.h \
   misc_ip.h \
   mmalloc.h \
   omSingularConfig.h \
   mpsr.h \
   mpsr_Get.h \
   mpsr_Put.h \
   mpsr_Timer.h \
   mpsr_Tok.h \
   mpsr_sl.h \
   ndbm.h \
   newstruct.h \
   pcv.h \
   pipeLink.h \
   pyobject_setup.h \
   run.h \
   sdb.h \
   silink.h \
   sing_dbm.h \
   sing_win.h \
   slInit.h \
   ssiLink.h \
   static.h \
   stype.h \
   subexpr.h \
   table.h \
   tok.h \
   utils.h \
   walk.h \
   feOpt.inc mpsr_Tok.inc iparith.inc feOptTS.inc feOptES.inc


libSingular_a_include_HEADERS   = $(SingularHEADERS)
libSingular_g_a_include_HEADERS = $(SingularHEADERS)

if ENABLE_FACTORY
  USE_FACTORY = -L${top_builddir}/factory
else
  USE_FACTORY =
endif

# noinst_HEADERS = feOpt.h
## TODO: install all the *.inc?!

#EXTRA_libSingular_a_SOURCES = feOpt.h
#EXTRA_libSingular_g_a_SOURCES = feOpt.h

BUILT_SOURCES=feOpt.inc mpsr_Tok.inc iparith.inc feOptTS.inc feOptES.inc
# plural_cmd.inc

#########################################################
# handle all the generated *.inc

AM_LDFLAGS = -L${top_builddir}/Singular -L${top_builddir}/numeric -L${top_builddir}/kernel -L${top_builddir}/libpolys/polys -L${top_builddir}/libpolys/coeffs -L${top_builddir}/libpolys/reporter -L${top_builddir}/libpolys/resources -L${top_builddir}/libpolys/misc $(USE_FACTORY) -L${top_builddir}/omalloc

EXTRA_PROGRAMS=feOpt gentable2 gentable1 feOptES feOptTS

#mpsr_Tok.cc: mpsr_Tok.inc
#iparith.cc: iparith.inc
#cntrlc.cc: feOpt.inc
#misc_ip.cc: feOpt.inc
## test.cc: iparith.inc


gentable2_SOURCES = gentable2.cc grammar.h tok.h table.h
# gentable2_LDADD = -lSingular -lnumeric -lkernel -lpolys -lcoeffs -lresources -lreporter -lmisc $(FACTORY_LIBS) -lomalloc $(NTL_LIBS) $(GMP_LIBS) ${USEPPROCSDYNAMICLDFLAGS} ${USEPPROCSDYNAMICLD}
gentable2_CFLAGS = -O3 -fomit-frame-pointer ${PIPE}
gentable2_CXXFLAGS = -O3 -fomit-frame-pointer --no-rtti -Wextra -Wall -Wno-long-long ${PIPE} $(CXXTEMPLFLAGS)
gentable2_CPPFLAGS = -DNDEBUG -DOM_NDEBUG


gentable1_SOURCES = gentable.cc grammar.h tok.h table.h
# gentable1_LDADD = -lSingular -lnumeric -lkernel -lpolys -lcoeffs -lresources -lreporter -lmisc $(FACTORY_LIBS) -lomalloc $(NTL_LIBS) $(GMP_LIBS) ${USEPPROCSDYNAMICLDFLAGS} ${USEPPROCSDYNAMICLD}
gentable1_CFLAGS = -O3 -fomit-frame-pointer ${PIPE}
gentable1_CXXFLAGS = -O3 -fomit-frame-pointer --no-rtti -Wextra -Wall -Wno-long-long ${PIPE} $(CXXTEMPLFLAGS)
gentable1_CPPFLAGS = -DNDEBUG -DOM_NDEBUG

# plural_cmd.inc: iparith.inc			       
			         
feOpt_SOURCES = feOpt.cc
# feOpt_LDADD = -lSingular -lnumeric -lkernel -lpolys -lcoeffs -lresources -lreporter -lmisc $(FACTORY_LIBS) -lomalloc $(NTL_LIBS) $(GMP_LIBS) ${USEPPROCSDYNAMICLDFLAGS} ${USEPPROCSDYNAMICLD}
feOpt_CFLAGS = -O3 -fomit-frame-pointer ${PIPE}
feOpt_CXXFLAGS = -O3 -fomit-frame-pointer --no-rtti -Wextra -Wall -Wno-long-long ${PIPE} $(CXXTEMPLFLAGS)
feOpt_CPPFLAGS = -DNDEBUG -DOM_NDEBUG -DGENERATE_OPTION_INDEX


feOptES_SOURCES = feOpt.cc
# feOptES_LDADD = -lSingular -lnumeric -lkernel -lpolys -lcoeffs -lresources -lreporter -lmisc $(FACTORY_LIBS) -lomalloc $(NTL_LIBS) $(GMP_LIBS) ${USEPPROCSDYNAMICLDFLAGS} ${USEPPROCSDYNAMICLD}
feOptES_CFLAGS = -O3 -fomit-frame-pointer ${PIPE}
feOptES_CXXFLAGS = -O3 -fomit-frame-pointer --no-rtti -Wextra -Wall -Wno-long-long ${PIPE} $(CXXTEMPLFLAGS)
feOptES_CPPFLAGS = -DNDEBUG -DOM_NDEBUG -DGENERATE_OPTION_INDEX -DESINGULAR 


feOptTS_SOURCES = feOpt.cc
# feOptES_LDADD = -lSingular -lnumeric -lkernel -lpolys -lcoeffs -lresources -lreporter -lmisc $(FACTORY_LIBS) -lomalloc $(NTL_LIBS) $(GMP_LIBS) ${USEPPROCSDYNAMICLDFLAGS} ${USEPPROCSDYNAMICLD}
feOptTS_CFLAGS = -O3 -fomit-frame-pointer ${PIPE}
feOptTS_CXXFLAGS = -O3 -fomit-frame-pointer --no-rtti -Wextra -Wall -Wno-long-long ${PIPE} $(CXXTEMPLFLAGS)
feOptTS_CPPFLAGS = -DNDEBUG -DOM_NDEBUG -DGENERATE_OPTION_INDEX -DTSINGULAR


########################### Singular* #########################

bin_PROGRAMS = Singular Singularg

## Singular: libSingular.a
## Singularg: libSingular_g.a

Singular_CFLAGS = -O3 -fomit-frame-pointer ${PIPE}
Singularg_CFLAGS = ${PIPE}

Singular_CXXFLAGS = -O3 -fomit-frame-pointer --no-rtti -Wextra -Wall -Wno-long-long ${PIPE} $(CXXTEMPLFLAGS)
Singularg_CXXFLAGS = -g -Wextra -Wall -Wno-long-long -pedantic ${PIPE} $(CXXTEMPLFLAGS)

Singular_SOURCES = tesths.cc
Singularg_SOURCES = tesths.cc

Singular_LDADD = libSingular.a -lnumeric -lkernel -lpolys -lcoeffs -lresources -lreporter -lmisc $(FACTORY_LIBS) -lomalloc $(NTL_LIBS) $(GMP_LIBS) ${USEPPROCSDYNAMICLDFLAGS} ${USEPPROCSDYNAMICLD}
Singularg_LDADD = libSingular_g.a -lnumeric_g -lkernel_g -lpolys_g -lcoeffs_g -lresources_g -lreporter_g -lmisc_g $(FACTORY_LIBS) -lomalloc_g $(NTL_LIBS) $(GMP_LIBS) ${USEPPROCSDYNAMICLDFLAGS}  ${USEPPROCSDYNAMICLD}

Singular_CPPFLAGS = -DNDEBUG -DOM_NDEBUG
# Singularg_CPPFLAGS =

########################### TEST #########################

TESTS_ENVIRONMENT = SINGULARPATH='${top_builddir}/libpolys/tests'
TESTS_ENVIRONMENT += SINGULAR_ROOT_DIR='${top_builddir}' 

TESTS=testg testr
check_PROGRAMS=$(TESTS)

testr_CFLAGS = -O3 -fomit-frame-pointer ${PIPE}
testg_CFLAGS = ${PIPE}

testr_CXXFLAGS = -O3 -fomit-frame-pointer --no-rtti -Wextra -Wall -Wno-long-long ${PIPE} $(CXXTEMPLFLAGS)
testg_CXXFLAGS = -g -Wextra -Wall -Wno-long-long -pedantic ${PIPE} $(CXXTEMPLFLAGS)

testr_SOURCES = test.cc
testg_SOURCES = test.cc

## testr: libSingular.a
## testg: libSingular_g.a

testr_LDADD = libSingular.a -lnumeric -lkernel -lpolys -lcoeffs -lresources -lreporter -lmisc $(FACTORY_LIBS) -lomalloc $(NTL_LIBS) $(GMP_LIBS) ${USEPPROCSDYNAMICLDFLAGS} ${USEPPROCSDYNAMICLD}
testg_LDADD = libSingular_g.a -lnumeric_g -lkernel_g -lpolys_g -lcoeffs_g -lresources_g -lreporter_g -lmisc_g $(FACTORY_LIBS) -lomalloc_g $(NTL_LIBS) $(GMP_LIBS) ${USEPPROCSDYNAMICLDFLAGS}  ${USEPPROCSDYNAMICLD}

testr_CPPFLAGS = -DNDEBUG -DOM_NDEBUG
# testg_CPPFLAGS =

#########################################################

CLEANFILES = $(TESTS) $(EXTRA_PROGRAMS)


#########################################################


feOpt.inc: feOpt
	./feOpt

feOptES.inc: feOptES
	./feOptES

feOptTS.inc: feOptTS
	./feOptTS

iparith.inc: gentable1
	./gentable1

mpsr_Tok.inc: gentable2
	./gentable2
