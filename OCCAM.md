[![Build Status](https://travis-ci.org/SRI-CSL/OCCAM.svg?branch=master)](https://travis-ci.org/SRI-CSL/OCCAM)


Introduction
============

This package includes OCCAM software, available from:
<https://github.com/ashish-gehani/OCCAM/> and <https://github.com/SRI-CSL/OCCAM>

Installation / Getting Started 
==============================

Prerequisites
-------------

Occam currently works fine on Linux, Mac OS X, and FreeBSD. You will
need an installation of [LLVM-3.5](http://llvm.org/docs/GettingStarted.html) and if you want to generate bitcode,
an install of [WLLVM](https://github.com/SRI-CSL/whole-program-llvm.git "Whole Program LLVM"). OCCAM also requires [Protocol Buffers](https://github.com/google/protobuf) library.

### Installation of LLVM and WLLVM on Ubuntu

OCCAM requires all the [dependencies of LLVM](http://llvm.org/docs/GettingStarted.html#requirements). In particular, you should install the following programs and libraries, listed below as Ubuntu packages:
```
sudo apt-get install build-essential vim curl bison flex bc libcap-dev git cmake libboost-all-dev libncurses5-dev python-minimal python-pip unzip 
```
You will need gcc/g++ 4.8 or later installed on your system.

LLVM can be installed using Ubuntu apt repository as below:
```
sudo apt-get install clang-3.5 llvm-3.5 llvm-3.5-dev llvm-3.5-tools  
```

Finally, make sure llvm-config is in your path:
```
sudo ln -sf ${LLVM_HOME}/bin/llvm-config-3.5 /usr/bin/llvm-config
```

### Installation of protobuf on Ubuntu


OCCAM requires [Protocol Buffers](https://github.com/google/protobuf) library. 

On Ubuntu, you can install its dependencies with:
```
sudo apt-get install autoconf automake libtool curl make g++ unzip
```
The quick way on Ubuntu to do this is:
```
sudo apt-get install libprotobuf-dev protobuf-compiler
```

**NOTE:** If you see error `"ImportError: No module named google.protobuf"` while running OCCAM, use `sudo pip install protobuf` to install protobuf. (Dependencies for pip : sudo apt-get install build-essential python-dev python-pip)

Building and Installing
-----------------------
After all the dependencies all installed, just use below commands from home directory of OCCAM.
```
make
make install
```

Using OCCAM
-----------

You can choose to record logs from the OCCAM 
tool by setting the following variables:

```
  export OCCAM_LOGFILE={absolute path to log location}
  export OCCAM_LOGLEVEL={INFO, WARNING, or ERROR}
```
