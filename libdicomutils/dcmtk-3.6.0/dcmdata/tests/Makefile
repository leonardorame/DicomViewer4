#
#	Makefile for dcmdata/tests
#



SHELL = /bin/sh
VPATH = ../include:../../config/include
srcdir = .
top_srcdir = ..
configdir = ../../config

include $(configdir)/Makefile.def

ofstddir = $(top_srcdir)/../ofstd
oflogdir = $(top_srcdir)/../oflog

LOCALINCLUDES = -I$(top_srcdir)/include -I$(ofstddir)/include -I$(oflogdir)/include
LIBDIRS = -L$(top_srcdir)/libsrc -L$(top_srcdir)/libi2d -L$(ofstddir)/libsrc -L$(oflogdir)/libsrc
LOCALLIBS = -ldcmdata -loflog -lofstd $(ZLIBLIBS)
I2DLIBS = -li2d

objs = tvrdatim.o tstpread.o tstpath.o tstchval.o i2dbmp.o
progs = tvrdatim tstpread tstpath tstchval i2dbmp


all: $(progs)

tvrdatim: tvrdatim.o
	$(CXX) $(CXXFLAGS) $(LDFLAGS) $(LIBDIRS) -o $@ $@.o $(LOCALLIBS) $(MATHLIBS) $(LIBS)

tstpread: tstpread.o
	$(CXX) $(CXXFLAGS) $(LDFLAGS) $(LIBDIRS) -o $@ $@.o $(LOCALLIBS) $(MATHLIBS) $(LIBS)

tstpath: tstpath.o
	$(CXX) $(CXXFLAGS) $(LDFLAGS) $(LIBDIRS) -o $@ $@.o $(LOCALLIBS) $(MATHLIBS) $(LIBS)

tstchval: tstchval.o
	$(CXX) $(CXXFLAGS) $(LDFLAGS) $(LIBDIRS) -o $@ $@.o $(LOCALLIBS) $(MATHLIBS) $(LIBS)

i2dbmp: i2dbmp.o
	$(CXX) $(CXXFLAGS) $(LDFLAGS) $(LIBDIRS) -o $@ $@.o $(I2DLIBS) $(LOCALLIBS) $(MATHLIBS) $(LIBS)


install: all

clean:
	rm -f $(objs) $(progs) $(TRASH)

distclean:
	rm -f $(objs) $(progs) $(DISTTRASH)


dependencies:
	$(CXX) -MM $(defines) $(includes) $(CPPFLAGS) $(CXXFLAGS) *.cc  > $(DEP)

include $(DEP)
