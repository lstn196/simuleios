# Makefile for general visualization 

CXX = clang++
#CXXFLAGS = -std=c++11 -g -Wall -march=native -fopenmp -fno-omit-frame-pointer -O2 -flto -Wno-sign-compare -fsanitize=address
CXXFLAGS = -std=c++11 -g -Wall -march=native -fopenmp -O2 -fno-omit-frame-pointer -flto -Wno-sign-compare

CAIROFLAGS = `pkg-config --cflags --libs cairo`
BINS = euler
OBJ = euler.o cairo_vis.o
DEPS = ../visualization/cairo/cairo_vis.h ../visualization/cairo/vec.h

$(BINS): $(OBJ)
	$(CXX) $(CXXFLAGS) -o $(BINS) $^ $(CAIROFLAGS)
	#convert -delay 5 -loop 0 /tmp/*.png frames/animation.gif

cairo_vis.o: ../visualization/cairo/cairo_vis.cpp $(DEPS)
	$(CXX) $(CXXFLAGS) -c -o $@ $< $(CAIROFLAGS)

%.o: %.cpp $(DEPS)
	$(CXX) $(CXXFLAGS) -c -o $@ $< $(CAIROFLAGS)

clean:
	rm -Rf $(BINS) $(OBJ) file*

