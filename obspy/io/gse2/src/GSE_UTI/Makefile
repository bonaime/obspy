# Makefile for gse2 functions and python wrapper
# Please adapt the includer for your requirement

INCLUDES= \
	-I .

CFLAGS = -g -O3
CC = gcc
LD = ld

gse_functions.so: buf.c gse_functions.c
	$(CC) $(CFLAGS) $(INCLUDES) -c buf.c gse_functions.c
	$(CC) $(CFLAGS) -shared -lm -o gse_functions.so buf.o gse_functions.o

gse_driver: gse_driver.c buf.c gse_functions.c
	$(CC) $(CLFAGS) -c gse_functions.c buf.c
	$(CC) $(CLFAGS) -o gse_driver gse_driver.c buf.o gse_functions.o

clean:
	rm -f gse_driver *.so *.o *.pyc leak.gse test.gse
