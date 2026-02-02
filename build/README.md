# CPP README

## Write a cpp file
> vi hello.cpp

## compile 
> g++ hello.cpp

This returns an output that is executable a.out. 

## run it
> ./a.out

## Name the output file
> g++ hello.cpp -o hello

## Why do we need forward declaration?
It is used to ensure the compiler knows the functions exsits somewhere. We do forward declaration in a header file. 

## Create a static library

### step 1: Define header file math_utils.h
### step 2: Create a definition file math_utils.cpp
### step 3: Compile the object. It will create math_utils.o file.
> g++ -c math_utils.cpp
### step 4: Create a static library. It will create libmathutils.a file.
> ar rcs  libmathutils.a math_utils.o
### NEXT step is to use the static library in main.cpp
We will compile + link
> g++ main.cpp libmathutils.a -o app

### Run the file
./app

## Create a dynamic library from static
### step 1: Compile with position independent code
> g++ -fPIC -c math_utils.cpp

### step 2: Create shared library
>g++ -shared math_utils.o -o libmathutils.so

### step 3: Use shared library
>g++ main.cpp -L. -lmathutils -o app

### step 4: run and use LD_LIBRARY_PATH

## cmake
CMake is build system generator tool. CMake automates and abstracts all of the manual steps

### creating CMakeLists.txt file
> mkdir project
> vi main.pp CMakeList.txt

### Content of CMakeLists.txt
```bash
    cmake_minimum_required(VERSION 3.16)
    project(hello_cmake)
    add_executable(hello main.cpp)
```

### build with cmake
```bash
    mkdir build
    cd build
    cmake ..
    cmake --build .
```

### run
```
./hello
```