# CHM

[![Build Status](https://travis-ci.org/ajkeller34/CHM.jl.svg?branch=master)](https://travis-ci.org/ajkeller34/CHM.jl)

A Julia package for extracting information from compiled help files (.chm).

## Usage

This package requires a shared library. In the `deps` folder you can find a .dll
file for Windows and a .dylib file for Mac OS X, either of which may or may not
work for your computer. Below you can find instructions on how I compiled them.
You will need to install the .dll file manually for now.

### Compiling ChmLib.dll on Windows 10

Prerequisites: Installation of Visual Studio Community 2015 or comparable. It
is a free download.

1. Download and extract a .zip file of [ChmLib](https://github.com/jedwing/CHMLib).
2. Inside there is another .zip file: `ChmLib-ds6.zip`. Extract that.
3. Open `ChmLib.dsw` in Visual Studio Community 2015.
4. Accept notice of the one-way upgrade (this project file is many years out of date).
5. Back in the file explorer, copy everything from `CHMLib-master/src` into
the directory `ChmLib-ds6`.
6. Copy the modified `chm_lib.h` from `deps/chm_lib.h` in this package into
the directory `ChmLib-ds6` (overwrite the old file).
7. In the "Solution Explorer" of VS Community 2015, right-click on ChmLib and
select Properties...
8. Click Configuration Manager...
9. Active solution configuration --> release
10. Active solution platform --> New...
11. New platform --> x64, copy settings from x86.
12. Make sure that project ChmLib is configured for Release and x64. Close the
Configuration Manager.
13. You should be back at a window ChmLib Property Pages. In the
list at the left you should select Configuration Properties -> General.
14. Change Project Defaults -> Configuration Type -> Dynamic Library (.dll).
15. Apply and OK.
16. Right click ChmLib in Solution Explorer and choose Build.
17. Verify in the output that you built Release x64 and a .dll file was
generated.
18. From `ChmLib-ds6\x64\Release` copy the .dll file to `C:\Windows\System32`.
19. Enjoy

### Compiling ChmLib.dylib on Mac OS X 10.11

1. Download and extract a .zip file of [ChmLib](https://github.com/jedwing/CHMLib).
2. From the Terminal, change paths to the `src` folder inside.
3. Run: `gcc -c -fpic chm_lib.c chm_lib.h lzx.c lzx.h`
4. Run: `gcc -dynamiclib -o ChmLib.dylib chm_lib.o lzx.o`
5. Copy the resulting `ChmLib.dylib` to the `deps` folder of this package.
6. Enjoy
