# CMake

Very complex build automation tools

Can be use in terminal or with GUI, supported both Windows and Linux

## Template

Hello world project as example

```cmake
cmake_minimum_required (VERSION 3.10)   # set cmake minimum version
project (hello_world VERSION 0.0.1)     # project version is optional
add_executable (hello_world main.c)     # executable name with source file
```

## libraries

CMake made linking against libraries easier than make by declare `find_package` for example

```cmake
find_package( OpenCV )
```

CMake will automatically search for `OpenCV` library if already installed on machine else will throw an error if CMake can't find it

Interestingly CMake version 3.14 or later can fetch libraries from URL for example

```cmake
include(FetchContent)
  FetchContent_Declare(
      cli11
      QUIET
      GIT_REPOSITORY https://github.com/CLIUtils/CLI11.git
      GIT_TAG v2.3.2
      )
FetchContent_MakeAvailable(cli11)  
```

CMake will pull git reposity to projecet and try to build against target executable

## If-else statement

```cmake
if (UNIX)
  # do something if UNIX
endif (UNIX)
```
