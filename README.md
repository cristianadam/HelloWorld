# HelloWorld
A C++ Hello World project, using CMake, ninja, ccache, and GitHub Actions.

## Instructions to build, test, install and run locally on Linux

**Prerequisites:**
- cmake 3.18.3+
- Ninja 1.10.1+
- g++/gcc

**Clean:**
```
$ rm -rf build/ bin/
```

**Prepare build to install in current directory:**
```
cmake -S . -B build -G Ninja -DCMAKE_INSTALL_PREFIX=.
```

**Build locally:**
```
cmake --build build
```

**Test:**
```
(cd build ; ctest)
```

**Install:**
```
cmake --install build
```

**Run:**
```
./bin/main
```

**Example output:**
```
$ rm -rf build/ bin/

$ cmake -S . -B build -DCMAKE_INSTALL_PREFIX=.
-- The C compiler identification is GNU 10.2.0
-- The CXX compiler identification is GNU 10.2.0
-- Detecting C compiler ABI info
-- Detecting C compiler ABI info - done
-- Check for working C compiler: /usr/bin/cc - skipped
-- Detecting C compile features
-- Detecting C compile features - done
-- Detecting CXX compiler ABI info
-- Detecting CXX compiler ABI info - done
-- Check for working CXX compiler: /usr/bin/c++ - skipped
-- Detecting CXX compile features
-- Detecting CXX compile features - done
-- Configuring done
-- Generating done
-- Build files have been written to: /home/wink/prgs/cmake/projects/gha-cmake-HelloWorld/build

$ cmake --build build
Scanning dependencies of target main
[ 50%] Building CXX object CMakeFiles/main.dir/main.cpp.o
[100%] Linking CXX executable main
[100%] Built target main

$ (cd build ; ctest)
Test project /home/wink/prgs/cmake/projects/gha-cmake-HelloWorld/build
    Start 1: main
1/1 Test #1: main .............................   Passed    0.00 sec

100% tests passed, 0 tests failed out of 1

Total Test time (real) =   0.00 sec

$ cmake --install build
-- Install configuration: ""
-- Installing: /home/wink/prgs/cmake/projects/gha-cmake-HelloWorld/bin/main

$ ./bin/main
Hello world
```
