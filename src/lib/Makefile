#definition of object files
out = lib.o
objects = $(patsubst %.cpp,%.o,$(wildcard *.cpp))

#rules
$(out) : $(objects)
	$(LD) -r $^ -o $@
	
%.o : %.cpp
	$(CXX) -c $(CFLAGS) $^ -o $@
#clean commands
.PHONY:clean
clean:
	rm -f $(objects)
