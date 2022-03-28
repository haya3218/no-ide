# IDE-less C/C++ Programming Guide with `CMake`

A guide on how in the actual fuck do you create a basic C/C++ application without an IDE (No Visual Studio, no Code::Blocks, and definitely no JetBrains).

The process is quite simple as you might think.

## Requirements

> The latest version of [CMake.](https://cmake.org/)

> A C++ compiler. This tutorial is primarily for C++, but this can *most likely* work with traditional C too. Examples include VC++ and GCC.

> Assortment of C++ libraries if you're gonna need it.

### Visual Studio Users

Using VC++ is currently not supported right now, but most commands here can be done on VC++, you might just need to swap on em.

## Windows Installation

1. Get the latest version of CMake and install it as normal.

2. If you're on Windows, you might already have VC++, which is bundled with Visual Studio versions.

If you *do not have* VC++ and are not interested in it, then you might need to try [MSYS2.](https://www.msys2.org/) This is a distribution of MingW-w64 for Windows *(of course)* that includes some neat stuff. You can also directly install libraries with it, so you don't have to go searching.

If that's a bit bloated for you, you might need to try something like [Nuwen.](https://nuwen.net/mingw.html) I am not providing support for this however, so do it at your own risk. I will be focusing on MSYS2 from now on. *For VC++ users, please refer to [here](#visual-studio-users).*

3. Proceed.

## Linux Installation

> A reminder that I'm mostly a Windows user, so please take these with a grain of salt.

1. Use your favorite package manager to install the essentials *(gcc, make, cmake, git, and libraries, most of the time starting with "lib")*

2. There is no step two. 

## Can we start programming now?

Ok ok fine.

First off, lets make our first hello world program.

```cpp
#include <iostream>

int main() {
    std::cout << "FUCK IM IN A PROGRAM" << "\n";
    
    return 0;
}
```

Lets recap this code.

```cpp 
#include <iostream>
```

This line tells the preprocessor (before compiling) to attach the *header* for `iostream.h`, in which its functions are layed out in a *source file*.

*Header files* are marked with `.h`, `.hxx` or `.hpp` file extensions, while *source files* are marked with `.c`, `.cxx` or `.cpp` file extensions.

```cpp
int main()
```

This is the default entry point of our application. Can also appear as

```cpp
int main(int argc, char** argv)
```

```cpp
std::cout << "message" << "\n";
return 0;
```

`std::cout` is a stream function *(indicated by <<)*. This sends whatever is streamed onto the standard output, which in this case is the command prompt. `"\n"` is what's called a line break character.

`return 0` indicates that the program has exited successfully. If it is not zero, then something might have gone wrong.

### Compiling

As we said before, we are using CMake to do all compiler work for us.

Many different `CMakeLists.txt` templates are available online, so you might need to Google a bit to get one you like.

To get started with compiling, do

```bash
cmake ..
```

All this does is make CMake choose the build generator for us, and puts them on the main directory.

To compile (fr), do

```bash
cmake --build
```

This will compile the program based on the build generator.

### you're done

Now go outside chum.
