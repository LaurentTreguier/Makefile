# Makefile
A simple makefile for C and C++ projects that should work on both Linux and Windows with Mingw.
It uses seperate directories for sources and headers and recursively looks for every file inside, so that you don't have to specify rules for every file yourself in the makefile.

### How to configure it

There are a few variables that can be changed in the first section of the makefile:
- `DIR_SRC`, `DIR_INC` and `DIR_OBJ` are the names of the sources, headers and objects directories
- `COMPILER` is the compiler you want to use
- `EXT` is the extension used by source files
- `TARGET` is the name of the target executable
- `COMMONFLAGS`, `CFLAGS` and `CXXFLAGS` contain C and C++ compiler flags
- `LIBS_WIN32` and `LIBS_LINUX` contain library linker flags for Windows and Linux

### How to use it

- `make init` will create the sources, headers and objects directories
- `make` will build the target
- `make clean` will purge the `DIR_OBJ` directory where object files and dependency files are stored
- `make foobar-depend` will purge foobar's object and dependency files;
this is used when moving a file and rebuilding dependencies without having to recompile everything
