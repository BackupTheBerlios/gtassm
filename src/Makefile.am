datarootdir = @datarootdir@

INCLUDES = $(GTASSM_CFLAGS)

AM_CFLAGS = \
        -Wimplicit -Wall \
        -DREGION=1

bin_PROGRAMS = gtassm

DEFS = @DEFS@ \
       -DPREFIX=\"@PREFIX@\"  \
       -DSRCFILEDIR=\"`pwd`\" \
       @GLOBAL_DEFINES@

gtassm_SOURCES = main.c

SRCFILEDIR=`pwd`

gtassm_LDFLAGS=$(GTASSM_LIBS)

gtassm_LDADD = 
