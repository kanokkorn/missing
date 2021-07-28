# Python3

## slice ops

Iterate over list with 2 increments

```py
x = [1, 2, 3, 4, 5]
x[::2]
[1, 3, 5]
```

Reverse list

```py
x[::-1]
[5, 4, 3, 2, 1]
```

## enumerate

Wrap an iterable with enumerate

```py
x = ['a', 'b', 'c']
for index, item in enumerate(x):
  print(index, item)
```

result will be

```py
0 a
1 b
2 c
```

## Value swapping

swapping between 2 variables

```py
x, y = 1, 2
y, x = x, y
```

## Decorators

Function inside functions

```python
def decorate(func):
  print('starting')
  func()
  print('ended')

@decorate
def main():
  print('hello')
```

output will be

```python
starting
hello
ended
```

## Lambda Expression

Expression function like mathematics

```python
def mul (x, y):
  return x * y
```

With Lambda Expression

```python
mul = lambda x, y: x * y
```

## Assignment Expression (Python3.8)

Assign value in middle of expression

Without Assignment Expression

```python
x = does.something()
while x is not false:
  return value
```

Example above can be written with Assignment Expression as

```python
while x := does.something()
  return value
```

## Virtual Environment

Virtual environment made python3 package management more easy, highly recommend when developing program that have lot of packages.

Get start with following command

```sh
python3 -m venv <path-to-project-folder>
```

In project folder will have something like

```sh
$ ls -lh
total 20K
drwxrwxr-x 2 user user 4.0K Jul 27 12:59 bin
drwxrwxr-x 2 user user 4.0K Jul 27 12:59 include
drwxrwxr-x 3 user user 4.0K Jul 27 12:59 lib
lrwxrwxrwx 1 user user    3 Jul 27 12:59 lib64 -> lib
-rw-rw-r-- 1 user user   70 Jul 27 12:59 pyvenv.cfg
drwxrwxr-x 3 user user 4.0K Jul 27 12:59 share
```

To activate virtual environment, run

```sh
source ./bin/activate
```

If virtual environment activated sucessfully will see indicate in path for example

```sh
(my-project) user@localhost:~/my-project$ 
```

Once finished or wanted to quit, to deactivate run following command

```sh
deactivate
```
