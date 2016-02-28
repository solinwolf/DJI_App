#definition of object files
out = lib.o
objects = $(patsubst %.cpp,%.o,$(wildcard *.cpp))

#rules
$(out) : $(objects)
	$(LD) -r $^ -o $@
	
%.o : %.cpp
	$(CXX) -c $(CFLAGS) $^ -o $@
#clean commands clean object files
.PHONY:clean
clean:
	rm -f $(objects)
