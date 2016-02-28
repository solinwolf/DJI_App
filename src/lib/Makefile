
out = lib.o
objects = $(patsubst %.cpp,%.o,$(wildcard *.cpp))

$(out) : $(objects)
	$(LD) -r $^ -o $@
	
%.o : %.cpp
	$(CXX) -c $(CFLAGS) $^ -o $@

.PHONY:clean
clean:
	rm -f $(objects)
