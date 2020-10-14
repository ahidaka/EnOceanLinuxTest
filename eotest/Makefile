#

TARGET = eotest

IFLAGS = -I/usr/include/libxml2
CFLAGS = -g -Wall -Wno-parentheses -Wno-unused-function -Wno-format-overflow $(IFLAGS)

all: $(TARGET)

eotest: eotest.o ptable.o control.o serial.o esp3.o
	gcc $(CFLAGS) eotest.o esp3.o ptable.o control.o serial.o -o eotest -lpthread -lxml2

eotest.o: eotest.c eotest.h ptable.h serial.h esp3.h ptable_extra.inc
	gcc $(CFLAGS) -c eotest.c

ptable.o: ptable.c eotest.h ptable.h ptable_extra.inc
	gcc $(CFLAGS) -c ptable.c

control.o: control.c eotest.h
	gcc $(CFLAGS) -c control.c

serial.o: serial.c serial.h esp3.h
	gcc $(CFLAGS) -c serial.c

esp3.o: esp3.c esp3.h
	gcc $(CFLAGS) -c esp3.c

clean:
	/bin/rm -f *.o *~ core $(TARGET)
