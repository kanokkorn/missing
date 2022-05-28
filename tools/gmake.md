# GNU Make or gmake

Example of GNU makefile

## Template

Hello world project as example

```makefile
# makefile 
CC = cc                                   # compiler
LDLIBS = -lm                              # libraries
CFLAGS = -std=c89 -Wall -Wextra -Werror\
         -Wconversion -Wshadow-Ofast\
         -pedantic                        # compiler flags
LDFLAGS = -fuse-ld=ld                     # linker flags

BIN = hello_world
SRC = $(wildcard *.c)                     # look for all .c files
OBJ = $(patsubst %.c, %.o, $(SRC))        # rename .c to .o files

DEBUG = 0

# condition example, set DEBUG to 1 is equivalent to #define DEBUG
ifeq ($(TEST), 1)
  CFLAGS += -DTEST
endif

# make sequence
all : $(OBJ) $(BIN)
# repeating prevention
.PHONY: all clean                         

$(OBJ): $(SRC)
  $(CC) $(CFLAGS) $^ -c
$(BIN): $(OBJ)
  $(CC) $(LD) $^ -o $@ $(LDLIBS)
clean :
  $(RM) *.o $(BIN)

# silent them if don't want to print out
.SILENT: clean  
```

## Flags

Flags that use in make

### Common use flags

- ```-j``` allow jobs, for example ```-j4``` will spawn 4 jobs to work simultaneous ,require some memory

- ```-n``` not actually run, just print


## Syntax

Syntax use in makefile

### Wildcard

Get name of everything, usually use with extension like ```*.c``` or ```*.cpp``` to grab a name of files with that extension

```makefile
$(wildcard pattern)
```

### Path substitution

Performs a textual replacement on the text 

```makefile
$(patsubst pattern, replacement, text)
```

useful for rename multiple files, like source files to object files for example

```makefile
OBJ = $(patsubst %.c, %.o, $(SRC))
```

Alternatively, this shorter version will output same result as ```patsubst```

```makefile
OBJ = $(SRC:.c=.o)
```
