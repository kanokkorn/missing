# CMake

Very complex build automation tools

Can be use in terminal or with GUI, supported both Windows and Linux

## Templete

Hello world project as example

```cmake
cmake_minimum_required (VERSION 3.10)   # set cmake minimum version
project (hello_world VERSION 0.0.1)     # project version is optional
add_executable (hello_world main.c)     # executable name with source file
```

## Package

CMake will find pkg-config if libraries have them like GTK or OpenCV

```cmake
find_package (PACKAGE REQUIRED)
```

## If-else statment

```cmake
if (UNIX)
  # do something if UNIX
endif (UNIX)
```
