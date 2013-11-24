all: clean checkEnv setFlags vecAdd_c vecAdd_reduction_c vecAdd_f vecAdd_reduction_f

.PHONY: checkEnv setFlags clean

checkEnv:
ifdef CRAY_PRGENVCRAY
    ifndef HMPP_BIN_PATH
        ifndef CRAY_ACCEL_TARGET
            $(error craype-accel-nvidia35 not loaded)
        endif
    else
        ifdef CRAY_ACCEL_TARGET
            $(error craype-accel-nvidia35 not compatible with CapsMC. Use cudatoolkit module)
        endif
    endif
endif
ifndef CRAY_CUDATOOLKIT_VERSION
    $(error cudatoolkit module not loaded)
endif

setFlags:
ifdef HMPP_BIN_PATH
    ifdef CRAY_PRGENVGNU
        CFLAGS = -std=c99
    endif
    ifdef CRAY_PRGENVINTEL
        CFLAGS = -restrict
    endif
else
    ifdef CRAY_PRGENVPGI
        CFLAGS = -acc
        FFLAGS = -acc
    endif
    ifdef CRAY_PRGENVCRAY
        CFLAGS = -hpragma=acc
        FFLAGS = -hacc
    endif
endif

vecAdd_c: vecAdd.c
	mkdir -p bin
	cc $(CFLAGS) -o bin/vecAdd_c vecAdd.c
vecAdd_reduction_c: vecAdd_reduction.c
	mkdir -p bin
	cc $(CFLAGS) -o bin/vecAdd_reduction_c vecAdd_reduction.c
vecAdd_f: vecAdd.f90
	mkdir -p bin
	ftn $(FFLAGS) -o bin/vecAdd_f vecAdd.f90
vecAdd_reduction_f: vecAdd_reduction.f90
	mkdir -p bin
	ftn $(FFLAGS) -o bin/vecAdd_reduction_f vecAdd_reduction.f90

clean:
	rm -rf bin
