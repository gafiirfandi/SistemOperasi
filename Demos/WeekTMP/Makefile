# REV02 Thu Dec  6 10:14:44 WIB 2018
# START Wed Dec  5 19:35:40 WIB 2018

CC            = gcc
CPP           = cpp
LDFLAGS       = 
CFLAGS        =
CPPFLAGS      =
DEPFLAGS      = -MM -MT $(@:.d=.o) 
OUTPUT_OPTION = -o $@
COMPILE       = $(CC) $(DEPFLAGS) $(CFLAGS) $(CPPFLAGS) -c
SRCS          = $(wildcard *.c)
OBJ           = $(SRCS:.c=.o)
DEP           = $(OBJ:.o=.d)
PROGS         = $(SRCS:.c=  )

all: main1 main2 main3 main4

main1: main1.o sub1.o sub2.o sub3.o
	$(CC) $(OUTPUT_OPTION) $^ $(LDFLAGS)
   
main2: main2.o sub1.o sub2.o
	$(CC) $(OUTPUT_OPTION) $^ $(LDFLAGS)
   
main3: main3.o sub1.o sub3.o
	$(CC) $(OUTPUT_OPTION) $^ $(LDFLAGS)
   
main4: main4.o sub2.o sub3.o
	$(CC) $(OUTPUT_OPTION) $^ $(LDFLAGS)

-include $(DEP)

%.d: %.c
	@$(CPP) $(CFLAGS) $< $(DEPFLAGS) > $@

.phony: clean cleandep all

clean:
	rm -rf $(OBJ) $(PROGS) $(DEP) 

