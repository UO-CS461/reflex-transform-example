#
# Makefile for building scanner.  You may prefer to use cmake, especially
# if you use CLion.  I don't know cmake well enough to give you a good
# portable CMakelists.txt
#
# Local tool paths and commands  (Varies by installation)
REFLEX_LIB = /usr/local/lib/libreflex.a
CCOPTS = -L /usr/local/lib
REFLEX_INCLUDE = /usr/local/include/reflex
REFLEX = reflex
# CC = g++ -std=c++11 -stdlib=libc++
CC = g++
PRODUCT = ../bin/py_strip

default: lexer

lex.yy.cpp:	py_strip.lxx
	$(REFLEX) --nodefault $^

lexer: ../bin/py_strip

../bin/py_strip:  lex.yy.cpp
	$(CC) $^ -o ${PRODUCT} -I $(REFLEX_INCLUDE) $(CCOPTS) -lreflex

clean:
	rm -f *.o
	rm -f lex.yy.cpp
	rm -f ${PRODUCT}


