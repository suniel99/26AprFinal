# General GEE Multitier GMT Makefile
#
# $Id: Makefile,v 1.2 2013/02/23 01:51:52 mokhov Exp $
#

BASE_GIPSY_DIR=../../../..

include $(BASE_GIPSY_DIR)/../Makefile.global

CLASSFILES = \
	GMTController.class \
	GMTInfoKeeper.class \
	GMTWrapper.class \
	SystemDSTServer.class

LIB_GIPSY_DIR = $(BASE_GIPSY_DIR)/../lib
CLASSPATH = $(LIB_GIPSY_DIR)/junit.jar:$(LIB_GIPSY_DIR)/marf.jar:$(LIB_GIPSY_DIR)/netcdfAll.jar:$(LIB_GIPSY_DIR)/jini-core.jar:$(LIB_GIPSY_DIR)/jini-ext.jar:$(LIB_GIPSY_DIR)/jms.jar:$(LIB_GIPSY_DIR)/imq.jar:$(LIB_GIPSY_DIR)/jung-visualization-2.0.1.jar:$(LIB_GIPSY_DIR)/jung-algorithms-2.0.1.jar:$(LIB_GIPSY_DIR)/jung-graph-impl-2.0.1.jar::$(LIB_GIPSY_DIR)/jgoodies/forms-1.3.0.jar:.

JFLAGS = $(COMMONJFLAGS) -classpath $(CLASSPATH) -sourcepath $(BASE_GIPSY_DIR)
JAVAC = javac

.SUFFIXES: .java .class

.java.class:
	$(JAVAC) $(JFLAGS) $< >> compile.log 2>&1

all: $(CLASSFILES)
	$(MAKE) -C demands $@

GMTController.class: GMTController.java
GMTInfoKeeper.class: GMTInfoKeeper.java
GMTWrapper.class: GMTWrapper.java
SystemDSTServer.class: SystemDSTServer.java

clean:
	rm -f *.class
	$(MAKE) -C demands $@

maintainer-clean: clean
	rm -f *.log *.diff *~
	$(MAKE) -C demands $@

# EOF
