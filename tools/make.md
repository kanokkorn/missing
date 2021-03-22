# Makefile

Build automation tools, very simple and come with most linux distribution

## Template

Hello world project as example

```makefile
# comment look like this
CC = cc  # compiler
LIBS = -lm  # link directories
CFLAGS = -std=c89 -Wall -Wextra -Ofast -pedantic
PROJECT_NAME = hello_world

DEBUG = 0

# condition example, set DEBUG to 1 is equivalent to #define DEBUG
ifeq ($(TEST), 1)
  CFLAGS += -DTEST
endif

$(PROJECT_NAME): main.c
  $(CC) $(CFLAGS) $(LIBS) $< -o $@
clean:
  rm $(PROJECT_NAME)

.SILENT: clean  # silent them if don't want to print out
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
