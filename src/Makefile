#define directoty
TOPDIR = ../
SRCDIR = $(TOPDIR)/src
export SRCDIR TOPDIR
#define compiler and linker
CXX = g++
LD = ld
export CXX LD
#define targets and objects
OBJECTS = $(patsubst %.cpp,%.o,$(wildcard *.cpp)) lib/lib.o
TARGET = $(TOPDIR)/output/DJI_AppS
export TARGET OBJECTS
#define compile parameters and link parameters
CFLAGS = -Wall -O3 -DPLATFORM_LINUX -DTINYXML_CFG -I$(SRCDIR)/include
LDFLAGS = -lpthread
export LDFLAGS CFLAGS 

#rules
$(TARGET) : $(OBJECTS)
	$(CXX) -o $(TARGET) $(OBJECTS) $(LDFLAGS)
%.o : %.cpp
	$(CXX) -c $(CFLAGS) $^ -o $@
lib/lib.o : lib/*.cpp	
	@cd $(SRCDIR)/lib && make
	
#clean commands	clean object files
.PHONY:clean
clean:
	@cd $(SRCDIR)/lib && make clean
	rm -r $(OBJECTS) $(TARGET)
	
	

