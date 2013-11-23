all: checkEnv clean vecAdd_cuf

.PHONY: checkEnv clean

vecAdd_cuf: vecAdd.cuf
	mkdir -p bin
	ftn -o bin/vecAdd_cuf vecAdd.cuf

checkEnv:
ifndef CRAY_PRGENVPGI
	$(error PrgEnv-pgi module not loaded)
endif

ifndef CRAY_CUDATOOLKIT_VERSION
        $(error cudatoolkit module not loaded)
endif

clean:
	rm -rf bin
	rm -f kernel.mod
