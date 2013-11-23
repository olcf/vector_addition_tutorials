all: clean vecAdd_cu

vecAdd_cu: vecAdd.cu
	mkdir -p bin
	nvcc -o bin/vecAdd_cu vecAdd.cu
clean:
	rm -rf bin
