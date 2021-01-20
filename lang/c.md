# C/C++

## Ternary Ops

Same as if-else statement but shorter and only supported 1 condition

Normally we would write if-else statement like this

```c
if (condition) {
  expression 1;
} else {
  expression 2;
}
```

But with Ternary Ops we could write

```c
condition ? expression 1 : expression 2;
```

## Elvis Ops

Like ternary ops but with expression 1 evaluted once

```c
expression 1 ?: expression 2;
```

## String Token

## Scanset

Accept only characters mentioned in scanset. For example 

```c
scanf("%[0-9]s", x);
```

That means scanf if accept only number 0-9 and ignore anything else

```^``` symbol means stop after found characters that mentions

```c
scanf("%[^S]s", x);
```

In this case, if uppercase s is found scanf will stop

## Case range

Switch-case with iterate number can be tedious to write 

For example

```cpp
switch(x){
  case 0:
    // do something
    ... 
  case 9:
    // do something
  default:
    // default
}
```

But with Case range, it can be written like this

```cpp
switch(x) {
  case 0 ... 9:
    // do something
  default:
    // default
}
```

## Designated Array Initializer
