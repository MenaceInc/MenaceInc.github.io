---
layout: post
title: "Getting started with C++ development on Windows"
date: "2017-05-20 17:07:08 +0100"
categories: c++ windows
---
### Initial MSYS2 setup

Go to the [MSYS2 website](http://www.msys2.org/) and download the installer appropriate for your system.
You'll need the msys2-i686-* installer for a 32bit version of Windows and the msys2-x86_64-* installer for 64bit Windows.

Install with the default options (it'll install to C:/msys64/) and then launch the MSYS2 shell at the end of the installer.

The very first thing you'll need to do is make sure all the packages are up to date. You can do this using the following command:
```shell
pacman -Syu
```

![]({{ "assets/images/MSYS2_1_initial_setup.png" | relative_url }})


This will download any updates from the MSYS2 repository and ensure that your system is working with the latest packages. You may need to do this a few times but keep running the above command until all packages are up to date.

**If there are any updates to pacman, you will get a warning saying you should close the window. At this point, press Ctrl + C THEN close the window.**

MSYS2 provides packages for both the GCC compiler suite and the LLVM/Clang compiler suite. For this setup, we'll only be dealing with using the GCC package.

### Installing GCC

Now to install the actual compiler you'll need to run your C++ code.
MSYS2 provides environments for both 32bit and 64bit targets. That is, what version of Windows you want your code to run on.

It's fairly safe to assume you'll be targetting 64bit machines so the following command will suffice.
```shell
pacman -Sy mingw-w64-x86_64-gcc mingw-w64-x86_64-gdb mingw-w64-x86_64-make
```
If you are wanting to target 32bit versions of Windows then you'll need to run the following command.
```shell
pacman -Sy mingw-w64-i686-gcc mingw-w64-i686-gdb mingw-w64-i686-make
```

### Testing GCC

Here we will quickly write a small Hello, World program and ensure that it is able to be compiled correctly.

Firstly though, you will need to switch to the MSYS2 MinGW environment which you can launch from your Start menu. Please ensure that you select the version that corresponds to the target system (MSYS2 MinGW 64bit for the 64bit environment).

After you've done that, you can check to see if GCC is installed and running correctly using `g++ --version`. You should see output similar to the below.

![]({{ "assets/images/MSYS2_2_gcc_version.png" | relative_url }})

From this shell, you can run `notepad test.cpp` in order to create a new .cpp file which will contain a C++ program.

Copy the below into Notepad and save the file (click File > Save or press Ctrl + S).
```c++
#include <iostream>

int main() {
    std::cout << "Hello, World!" << std::endl;
    return 0;
}
```

For this very simple program, you can then use `g++ test.cpp -o hello` to compile the program into an executable binary (.exe file) and then use `./hello` to run it.

You can even combine the two commands like so.
```shell
g++ test.cpp -o hello && ./hello
```

You should end up with something like the screenshot below.

![]({{ "assets/images/MSYS2_3_hello_world.png" | relative_url }})

Congratulations! You just setup a basic C++ environment to develop programs in Windows.



### Further setup

At this point, I would recommend installing a full IDE (Integrated Development Environment) such as [CLion](https://www.jetbrains.com/clion/) or [KDevelop](https://www.kdevelop.org/) so that you can more easily manage projects that span across many files and folders.

CLion is a great IDE that is free to students although does cost £69 for the first year if you don't qualify for a free licence. KDevelop is available completely for free.

Both of the above IDEs use CMake as their project model so you may need to look over the CMake documentation [available here](https://cmake.org/documentation/).
