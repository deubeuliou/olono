OPTS = -g -p -Wall #-pedantic

default: all
all: libs olono

libs: libIA libDisplay libPlay libCases

olono:main.o
	gcc -o olono main.o ../lib/libCases.so ../lib/libIA.so  ../lib/libDisplay.so ../lib/libPlay.so $(OPTS)

libIA:
	gcc -c ../lib/libIA.c -o ../lib/libIA.o $(OPTS)
	gcc -o ../lib/libIA.so -shared ../lib/libIA.o $(OPTS)

libDisplay:
	gcc -c ../lib/libDisplay.c -o ../lib/libDisplay.o $(OPTS)
	gcc -o ../lib/libDisplay.so -shared ../lib/libDisplay.o $(OPTS)

libPlay:
	gcc -c ../lib/libPlay.c -o ../lib/libPlay.o $(OPTS)
	gcc -o ../lib/libPlay.so -shared ../lib/libPlay.o $(OPTS)

libCases:
	gcc -c ../lib/libCases.c -o ../lib/libCases.o $(OPTS)
	gcc -o ../lib/libCases.so -shared ../lib/libCases.o $(OPTS)

main.o:
	gcc -c main.c $(OPTS)

doc:
	doxygen ../doxygen/Doxyfile
	$(MAKE) -C ../doxygen/latex -f Makefile

clean:
	rm -v *.o
	rm -v ./olono

mrproper:
	rm -v *.o
	rm -v ./olono
	rm -vR ../doxygen/html ../doxygen/latex

