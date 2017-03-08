## llvm-epp 
Efficient Path Profiling using LLVM 

[![Build Status](https://travis-ci.org/sfu-arch/llvm-epp.svg?branch=master)](https://travis-ci.org/sfu-arch/llvm-epp)

This tool is still in alpha and under active development. 

## Requires 

1. LLVM 3.8
2. llvm-lit 
3. gcc-5

## Build 

1. `mkdir build && cd build`
2. `cmake -DCMAKE_BUILD_TYPE=Release .. && make -j 8`
3. `sudo make install`

## Test

To run the tests, install [lit](https://pypi.python.org/pypi/lit) from the python package index. 

1. `pip install lit`
2. `cd build`
3. `lit test/srcs`  

## Usage

1. `clang -c -g -emit-llvm prog.c`
2. `llvm-epp prog.bc -o prog`
3. `clang prog.epp.bc -o exe`-lepp-rt
4. `./exe`
5. `llvm-epp -p=path-profile-results.txt prog.bc`

## Known Issues 

1. Multi-thread support  
2. C++ Exceptions  
3. Support `setjmp` and `longjmp`

## License 

The MIT License

