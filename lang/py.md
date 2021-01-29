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
