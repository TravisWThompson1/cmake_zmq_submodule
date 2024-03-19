# Using ZMQ as a Submodule with CMake
This repository serves as an example of how to include ZMQ (cppzmq and libzmq) as a submodule in a project that uses CMake.

## Clone the Repository and Submodules
Clone the repository using the git clone command and clone the submodules with the git submodule commands.
```
git clone https://github.com/TravisWThompson1/cmake_zmq_submodule
cd cmake_zmq_submodule/
git submodule update --init
```

## Prerequistes
(Optional) If you want to specify a particular toolchain to build this library, set the environment variables CC and CXX as the paths to the C and C++ toolchains you want to use.
```
export CC=/usr/bin/gcc
export CXX=/usr/bin/g++
```

## How to Build
To build the repository, create a build folder, configure the project with cmake, and build the libraries and executable with make.

```
# Create build folder and change directory into it
mkdir build
cd build/

# Configure the build system and build the repository
cmake ../
make
```

## Run the Example Server/Client Executables
To run the example server and client executables, open two terminals and run the server and then client executables.
```
# Terminal 1
cd build/
./server

# Terminal 2
cd build/
./client
```
