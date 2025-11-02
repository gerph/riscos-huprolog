##
## Oyster2 Programming System 
## Makefile Release 1.02 10/05/90
##
## please check the contents of this directory
## 
## arith.c atoms.c atoms.h bootstrap contents
## datab.c db3.c errors.h eval.c exec.c files.h help.c
## io.c makefile manager.c manager.h maxvars.h memory.c
## misc.c nurprl oinit.c oyster.c read.c rulebase
## save.c sys.c systems.h types.h uni.c
## user.c win.c window.h write.c
## 
##
SHELL=/bin/sh
SYSTEM=ARCHY
CC=cc
CFLAGS= -Wda -D$(SYSTEM) -DDYNMEM
LDFLAGS=
BIN= ^.^.bin

OBJ =   arith.o atoms.o datab.o eval.o exec.o  \
        io.o manager.o memory.o misc.o prolog.o read.o \
        save.o sys.o uni.o user.o write.o 

PORTOBJ = unixio.o

.c.o:
        cc $(CFLAGS) -c c.$*


prolog :  $(OBJ) $(PORTOBJ) 
        link $(SEPID) -o $@ $(OBJ) $(PORTOBJ) $.Clib.o.Stubs $(LDFLAGS)

# Needed because when in ANSI mode big arrays are
# put in initialized data!  Yuk.

# memory.o:
#       cc -pcc $(CFLAGS) -c c.$*


$(OBJ) oyster.o : systems.h errors.h types.h atoms.h 

atoms.o datab.o exec.o manager.o \
        memory.o misc.o save.o uni.o : manager.h
datab.o eval.o help.o io.o prolog.o \
        read.o sys.o write.o : files.h window.h
datab.o read.o write.o : maxvars.h
win.o : window.h


install :
        delete $(BIN).prolog
        rename prolog $(BIN).prolog

