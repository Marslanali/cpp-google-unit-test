# cpp-google-unit-test
unit test using Google C++ test framework

## Linux Dependencies

- [GTest](https://github.com/google/googletest)
- GCC
- CMake
- GNU Make

### Getting GTest on Ubuntu

```
sudo apt-get install libgtest-dev
sudo apt-get install cmake
cd /usr/src/gtest
sudo cmake CMakeLists.txt
sudo make
sudo cp *.a /usr/lib
```

### Building GTest on Ubuntu

```
cd ~\cpp-google-unit-test
mkdir build
cd build
cmake ..
make
```

### Running GTest executable

```
$ ./UTest 
```

```
[==========] Running 4 tests from 1 test case.
[----------] Global test environment set-up.
[----------] 4 tests from SquareRootTest
[ RUN      ] SquareRootTest.PositiveNos
[       OK ] SquareRootTest.PositiveNos (0 ms)
[ RUN      ] SquareRootTest.NegativeNos
[       OK ] SquareRootTest.NegativeNos (0 ms)
[ RUN      ] SquareRootTest.GreaterNos
[       OK ] SquareRootTest.GreaterNos (0 ms)
[ RUN      ] SquareRootTest.LessNos
[       OK ] SquareRootTest.LessNos (1 ms)
[----------] 4 tests from SquareRootTest (1 ms total)

[----------] Global test environment tear-down
[==========] 4 tests from 1 test case ran. (1 ms total)
[  PASSED  ] 4 tests.
```


## Window Dependencies

- [GTest](https://github.com/google/googletest)
- MinGW
- CMake
- GNU Make

First get [GTest](https://github.com/google/googletest) in your root folder. 

```
cd ~\cpp-google-unit-test
git clone https://github.com/google/googletest.git
```

Open `cmd` or `power shell` as an administrator.

### Building GTest on windows

On windows `powershell` type: 

```
cd ~\cpp-google-unit-test
mkdir build
cd build
cmake .. -G "MinGW Makefiles"
make
```

- The flag `-G "MinGW Makefiles"` is necessary if you are using `power shell` or `cmd` in windows. 
  Bydefault `make` is set to visual studio platform toolset. 


### Running GTest executable

On windows `powershell` type:

```
& ".\UTest.exe"
```

```
[==========] Running 4 tests from 1 test case.
[----------] Global test environment set-up.
[----------] 4 tests from SquareRootTest
[ RUN      ] SquareRootTest.PositiveNos
[       OK ] SquareRootTest.PositiveNos (0 ms)
[ RUN      ] SquareRootTest.NegativeNos
[       OK ] SquareRootTest.NegativeNos (0 ms)
[ RUN      ] SquareRootTest.GreaterNos
[       OK ] SquareRootTest.GreaterNos (0 ms)
[ RUN      ] SquareRootTest.LessNos
[       OK ] SquareRootTest.LessNos (1 ms)
[----------] 4 tests from SquareRootTest (1 ms total)

[----------] Global test environment tear-down
[==========] 4 tests from 1 test case ran. (1 ms total)
[  PASSED  ] 4 tests.

```


