# Makefile

Build automation tools, very simple and come with most linux distribution

## Template

Hello world project as example

```makefile
# comment look like this
cc = gcc  # compiler
ld = -lm  # link directories
cflag = -std=c99 -Wall -Wextra -Ofast
project_name = hello_world

$(project_name): main.c
  $(cc) main.c $(cflags) $(ld) -o $(project_name)
clean:
  rm $(project_name)

.SILENT: clean  # silent them if don't want to print out
```

## Flags

run make with all available threads

```sh
make -j`nproc`
```

just print without run

```sh
make -n
```
