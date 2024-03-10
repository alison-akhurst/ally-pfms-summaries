Week 1 
=========================
# Things we did this week - Syntax and Examples
## primitive data types, and their memory footprint


## pointers, passing by reference and scope**


## functions


## loops


## structures 

# Module Summary Questions

## 1. Understand what are source and header files

Very simply: 
- **Header files** --> are the keys to access functionality (#included not compiled)
- **Source files** -->  implement the functionality (compiled not #included)

In more technical terms: *...Header files usually have a .h extension, but you will occasionally see them with a .hpp extension or no extension at all. The primary purpose of a header file is to propagate declarations to code (.cpp) files.*

You can make your own header files and you can use standard library header files.

## 2. Compile your code on Ubuntu via the command line
Navigate to the appropriate folder using the `cd` command. Let's say we want to run tutorial Week 03

`cd /home/ally/git/pfms-2024a-alison-akhurst/tutorials/week03/starter`

**Hint** your folder should contain your CMakeLists.txt file!

Make a build folder using the `mkdir` command

`mkdir build`

Run CMake

For in the build folder, with CMake lists in the parent folder:

`cmake ..`

For in the folder containing CMake lists:

`cmake .`

Make the executables

`make`

You can now run the executables using `./`. For example, if we had a `circles` executable we would run it like this:

`./circles`


## 3. Compile your code on Ubuntu via vscode IDE

The main things here are to make sure you have nagivated into the folder containing ONLY the code and CMakeLists.txt file. Otherwise the CMake toolbar won't appear! If ya'll need help give someone a holler and we can show you what buttons to push.


## 4.Follow the syntax of CMakeLists.txt and add a new source file and executable

To add new executables you need to ammend the inputs for the `add_executable()` function in the CMakeLists.txt file. See the code snippet below 
```
# The minimum version of CMake Required 
cmake_minimum_required (VERSION 2.6)

# Any project name will suffice, this has connotaions when using advanced CMake Features
project (shapes)

# This is added to c++11 features
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

# To add executables provide the executable name followed by a list of source files
# There must be exactly one function called main in each executable

# This executable demonstrates the declaration, implementation, and use of the rectangle class
# Notice we now have two source files, one has our main, the other implements our rectangle class
add_executable(shapes_eg main.cpp circle.cpp shape.cpp rectangle.cpp)
```
In this example, if we wanted to add a newly created triangle.cpp file, the  command would look like 

`add_executable(shapes_eg main.cpp circle.cpp shape.cpp rectangle.cpp triangle.cpp)`


## 5.Select a suitable data type for your variable



## 6.Use a pointer to a variable, change the variable contents, pass the variable by reference to a function




## 7.Use function return values as well as changing the variable passed to function




## 8.Understand limitations of C style arrays




**9.Use structures, access the varaibles and expand structure with a new variable**




**10.Use a STL vector, store data in the vector dynamically changing the size, determine the size, pre-allocate the vector size**




**11.Implement a state machine using enums for states**


