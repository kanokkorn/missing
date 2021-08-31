# Makefile

Build automation tools, very simple and come with most linux distribution

## Template

Hello world project as example

```makefile
# makefile 
cc = cc                                   # compiler
libs = -lm                                # libraries
cflags = -std=c89 -Wall -Wextra -Werror\
         -Wconversion -Wshadow-Ofast\
         -pedantic                        # compiler flags
ld = -fuse-ld=ld                          # linker flags

bin = hello_world
src = $(wildcard *.c)                     # search for all .c files
obj = $(patsubst %.c, %.o, $(src))        # convert .c to .o files

DEBUG = 0

# condition example, set DEBUG to 1 is equivalent to #define DEBUG
ifeq ($(TEST), 1)
  CFLAGS += -DTEST
endif

# make sequence
all : $(obj) $(bin)
# repeating prevention
.PHONY: all clean                         

$(obj) : $(src)
  $(cc) $(cflags) $^ -c
$(bin) : $(obj)
  $(cc) $(ld) $^ -o $@ $(libs)
clean :
  $(RM) *.o $(bin)

# silent them if don't want to print out
.SILENT: clean  
```

## Flags

run make with all available threads

```sh
make -j`nproc`
```

for shorter version

```sh
make -j
```

just print without run

```sh
make -n
```

## Syntax
