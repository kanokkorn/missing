# CMake

very popular build automation tools for building C/C++ project, we may find major libraries using `cmake` in projects

## Usage

To use `cmake`, first we need a text file called `CMakeLists.txt` (which may find basic configuration below) and project structure like

```sh
drwxrwxr-x   - mitsuha mitsuha 25 Jun 00:45 build
.rw-rw-r-- 532 mitsuha mitsuha 28 Jun 23:43 CMakeLists.txt
drwxrwxr-x   - mitsuha mitsuha 25 Jun 00:49 src
```

Depends on how we organise, but most project will have structure like 

- `src` for source files 
- `lib` for external libraries
- `build` for `cmake` generate configuration to build target binary

To build a binary file, create `build` if not

```sh
cd build/
```

After than called `cmake` to generate a configuration

```sh
cmake ..
```

`cmake` will generate configuration based on ours system compiler, linker .. Etc

When generate is complete, run command depends on system

```sh
make && make install
```

## basic CMakeLists.txt template

Hello world project as example

```cmake
cmake_minimum_required (VERSION 3.10)   # set cmake minimum version

project(hello_world VERSION 0.1.0)      # project version is optional

add_executable (hello_world main.c)     # executable name with source file
target_link_libraries(
    hello_world
    ${LIBS}
)
```

## Managing libraries

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

CMake will pull git reposts to project and try to build against target executable

## If-else statement

If-else statement can be use for conditional build options like target difference platform or architecture

```cmake
if (UNIX)
  # build option for UNIX platform
endif (UNIX)
```
