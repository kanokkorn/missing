# C/C++

## Type casting

Convert from one type to another type

```c
(type) expression
```

For example, casting int to float

```c
int x = 1;
x = (float) x;
```

## Comma Ops

both statements are evaluated, but only last statement return value

```c
int x = (printf("the value is"), getValue());
```

For-loop example

```c
for (int x = 0; x < 10; x++, random_func()) {
  // do something after random_func
}
```

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

Can be mapping ```enum``` or assign value in array 

For assign value

```c
int x[6] = { [2] = 31, [5] = 54};
int x[6] = { 0, 0, 31, 0, 0, 54};
```

For mapping ```enum```

```c
enum color {
  black,
  green,
  white,
}
```

Value in ```[]``` will map to other array

```c
constexpr uint32_t color_value[] = {
  [black] = 0x000000,
  [white] = 0xffffff,
  [green] = 0x00ff00,
}
```

## Computed goto

Alternative to switch-case, can increase loop speed up to 15% ~ 30% but also increase codebase

This trick depends on CPU architecture/branch prediction it may not speed up all case

```c
void func(void) {
  void* p = &&label;
  goto* p;
label:
  return;
}
```
