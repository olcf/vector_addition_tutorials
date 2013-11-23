all: clean vecAdd_c vecAdd_f

vecAdd_c: vecAdd.c
	mkdir -p bin
	cc -o bin/vecAdd_c vecAdd.c
vecAdd_f: vecAdd.f90
	mkdir -p bin
	ftn -o bin/vecAdd_f vecAdd.f90
clean:
	rm -rf bin
