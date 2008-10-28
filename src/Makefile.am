datarootdir = @datarootdir@

INCLUDES = $(QTASSM_CFLAGS)

AM_CFLAGS = \
        -Wimplicit -Wall \
        -DREGION=1

bin_PROGRAMS = qtassm

DEFS = @DEFS@ \
       -DPREFIX=\"@PREFIX@\"  \
       -DSRCFILEDIR=\"`pwd`\" \
       @GLOBAL_DEFINES@

qtassm_SOURCES = main.c

SRCFILEDIR=`pwd`

qtassm_LDFLAGS=$(QTASSM_LIBS)

qtassm_LDADD = 
