all: clean vecAdd_cu

vecAdd_cu: vecAdd.cu
	mkdir -p bin
	nvcc -arch=sm_35 -o bin/vecAdd_cu vecAdd.cu
clean:
	rm -rf bin
