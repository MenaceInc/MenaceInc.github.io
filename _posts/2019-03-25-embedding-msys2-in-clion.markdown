---
layout: post
title: "Embedding MSYS2 terminal in CLion (Windows)"
date: "2019-03-25 03:33:00 +0000"
---

Using CLion for C++ development is pretty great for numerous reasons and on Windows, I prefer using Mingw-w64 for compilation. The easiest way to [install it](https://menaceinc.com/2017/05/getting-started-with-c-development-on-windows/) and manage libraries in my opinion is to use MSYS2. MSYS2 provides a terminal interface via mintty which works well but it gets annoying having to jump between CLion and a separate terminal window. CLion however provides a method of embedding a terminal within the CLion UI.

### The problem

There is an issue though in that it isn't possible to just put `C:\msys64\usr\bin\bash.exe --login` into the shell path setting and be done with it. CLion will complain that it cannot open a terminal when you click the terminal button.

It is possible to point it to `C:\msys64\mingw64.exe` but now the terminal button will launch a separate window for the MSYS2 terminal. That's the exact thing I wanted to avoid!

### The solution

What we have to do instead is write a small .bat file with a command to launch the terminal and point CLion to that batch file. I recommend making the batch file in the same folder that MSYS2 is installed in and name it clion.bat.

The contents of the batch file should be
```shell
@echo off
set MSYSTEM=MINGW64 && set CHERE_INVOKING=1 && C:\msys64\usr\bin\bash.exe --login
```

What the above command does is set two environment variables then launch the MSYS2 terminal directly.

For MSYSTEM, you can use MSYS, MINGW32 or MINGW64 which corresponds to the base MSYS terminal, the 32bit Mingw-w64 terminal and the 64bit Mingw-w64 terminal respectively.

The CHERE_INVOKING variable is so that the terminal will change the directory to the current project directory when the terminal button is clicked in CLion.

All of the above assumes that the 64bit version of MSYS2 was installed to the default directory. If you have installed it elsewhere, you would need to adjust the filepaths accordingly.
