# BSD Make or bmake

BSD makefile use by *BSD system like FreeBSD, NetBSD

## Template

This example is compatiable with GNU make

```makefile
BIN = hello

.SUFFIXES: .c .o
.c.o:
  ${CC} ${CFLAGS} -c $<

${BIN}: hello.o
  ${CC} ${CFLAGS} -o $@ hello.o

hello.o : hello.h

clean:
  rm -rf hello.o ${BIN}

.PHONY: clean
```

## Key differance from GNU Make

Here's some key differance from GNU make

### Automatic variable



### Variable Modifiers

### Condition

Instead of GNU make ```ifeq``` BSD make use more C-like syntax 

```makefile
.if ${VAR} == 'string'
  expression
.endif
```