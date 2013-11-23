all: checkEnv clean vecAdd_cu

.PHONY: checkEnv clean

vecAdd_cu: vecAdd.cu
	mkdir -p bin
	nvcc -arch=sm_35 -o bin/vecAdd_cu vecAdd.cu

checkEnv:
ifndef CRAY_CUDATOOLKIT_VERSION
	$(error cudatoolkit module not loaded)
endif

clean:
	rm -rf bin
