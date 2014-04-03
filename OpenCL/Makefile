all: checkEnv clean vecAdd_cl vecAdd_cc_cl

.PHONY: checkEnv clean

vecAdd_cl: vecAdd.c
	mkdir -p bin
	cc -lOpenCL -o bin/vecAdd_cl vecAdd.c

vecAdd_cc_cl: vecAdd.cc
	mkdir -p bin
	CC -lOpenCL -o bin/vecAdd_ccl vecAdd.cc

checkEnv:
ifndef CRAY_CUDATOOLKIT_VERSION
	$(error cudatoolkit module not loaded)
endif

clean:
	rm -rf bin
