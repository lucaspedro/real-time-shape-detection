CXX=g++
ENABLE_OPENCL= -I/opt/AMDAPPSDK-3.0/include -I/opt/AMDAPPSDK-3.0/include/SDKUtil/ -L/opt/AMDAPPSDK-3.0/lib/x86_64 -lOpenCL
CXXFLAGS= -std=c++11 `pkg-config --cflags --libs opencv` $(ENABLE_OPENCL)
DEPS = 
OBJ = Moments.o

$(info INCLUDE_DIRS is $(INCLUDE_DIRS))
#-I/opt/AMDAPPSDK-3.0/include -L/opt/AMDAPPSDK-3.0/lib/x86_64 -lOpenCL

all: welcome clean Hu
	
%.o: %.cpp $(DEPS)
	@echo Compiling $< with $(CXX)...
	$(CXX) -c -o $@ $< $(CXXFLAGS)

Hu: $(OBJ)
	$(CXX) -o $@ $^ $(CXXFLAGS)

clean:
	rm -f *.o *~ *.clb Hu
	
welcome:
	@echo ---------------------------------------
	@echo ---- WSW OpenCV Geometric moments -----
	@echo ---------------------------------------
	
# (useful when debugging)
# redirect compilation output to less:
# less < <(make 2>&1)

