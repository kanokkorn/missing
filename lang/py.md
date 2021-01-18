# Python3

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
