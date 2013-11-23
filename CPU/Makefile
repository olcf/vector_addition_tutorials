build/vecAdd_c.out: vecAdd.c
	mkdir -p build
	cc vecAdd.c -o build/vecAdd.out

build/vecAdd_f.out: vecAdd.f90
	mkdir -p build
	ftn vecAdd.f90 -o build/vecAdd.out

clean:
	if [ -d build ]; then rm -Rf build; fi
