PATH 			:= /usr/bin/: $(PATH)

VS				= "C:\Program Files (x86)\Microsoft Visual Studio 11.0\VC\bin"
CC				= cl.exe
CFLAGS 			= -c
INCLUDES		= -I "c:\Program Files (x86)\Microsoft Visual Studio 12.0\VC\include"
LIB_VS			= "/LIBPATH:c:\Program Files (x86)\Microsoft Visual Studio 12.0\VC\lib"
LIB_SDK			= "/LIBPATH:c:\Program Files (x86)\Windows Kits\8.1\Lib\winv6.3\um\x86"

CC 				= gcc
CFLAGS 			= -c
LDFLAGS			= -o
DBG				= -g
OBJ				= main.o function.o

all: main.exe 

.PHONY: main.o function.o

main.exe: $(OBJ)
#	gcc		-o 			main.exe 	main.o function.o
	$(CC) 	$(LDFLAGS) 	$@ 			$^ 

main.o function.o: %.o: %.c
	$(CC) 	$(CFLAGS) $(DBG)	$<
	
	@echo "Echo": $(MAKEFILES)
#---------------------------------------------------------------------

vs: vs.exe

vs.exe: main.obj function.obj
	vs_link $(LIB_VS) $(LIB_SDK) /OUT:$@ $^
	
main.obj: main.c
	$(CC) $(CFLAGS) $(INCLUDES) $^

function.obj: function.c
	$(CC) $(CFLAGS) $^
	
print: $(wildcard *.c)
	ls -la  $?
	@echo $?
	
clean:
	rm -f one two three
	rm *.o *.obj *.exe

target.exe: main.cpp function.cpp
    # Target with extension
	@echo $(MAKE)	#
	@echo $*		# 
	@echo $@		# 
	@echo $?		# 
	@echo $^	
main.cpp:
	@echo main.ccc
function.cpp:
	@echo function.ccc
	
#--------------------------------------------------------------------

autosar:
	@echo $(shell uname)
	export UNAME:=$(shell uname)


ifneq ($(findstring Darwin,$(UNAME)),)
  SHELL:=/bin/bash
  export SED=/opt/local/bin/gsed
else
	export SED=sed
endif  