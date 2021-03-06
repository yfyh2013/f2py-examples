[![Build Status](https://travis-ci.org/scivision/f2py-examples.svg?branch=master)](https://travis-ci.org/scivision/f2py-examples)
[![Coverage Status](https://coveralls.io/repos/github/scivision/f2py-examples/badge.svg?branch=master)](https://coveralls.io/github/scivision/f2py-examples?branch=master)
[![Maintainability](https://api.codeclimate.com/v1/badges/267260ede653e9a5e2f4/maintainability)](https://codeclimate.com/github/scivision/f2pyExamples/maintainability)

# f2py Examples


Simple examples of using `f2py` to get high-speed Fortran integrated with Python easily. 
These examples are also useful to troubleshoot problems with `f2py`.

## Build

Fortran compiler is needed:

* Mac: `brew install gcc`
* Linux: `apt install gfortran`  or  `yum install gfortran`
* [Windows](https://www.scivision.co/install-latest-gfortran-on-ubuntu/)

### Install


    pip install -e .

This will compile the Fortran code (in `.f` and `.f90` files) and create
a file `pyprod.*` where `*` depends on your operating system and Python version. 

* Linux/Mac: `.so` 
* Windows: `.pyd`

## Examples

### Fortran Intents

    python f2py_demo.py

You will see the output:

    x = 3
    y = 2
    x * y = 6.0
    Your system did this in Python using Fortran-compiled library

### Fortran comment syntax

Fortran 77 is officially full-line comments only. Inline comments are
not allowed with `f2py` as a result in Fortran 77 files. Demonstrate
this with:

    f2py -m badcomment -c badcomment.f

## Troubleshooting f2py

`f2py` normally Just Works on Linux, Mac and 
[Windows Subsystem for Linux](https://www.scivision.co/tag/#windows-subsystem-for-linux).
However, Windows itself can be more challenging due to inconsistencies in Microsoft Visual Studio.

See the Windows f2py installation guide and troubleshooting 
[guide](https://www.scivision.co/f2py-running-fortran-code-in-python-on-windows/).
