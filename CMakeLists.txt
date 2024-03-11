# --------------------------------------------
# Project Setup
# --------------------------------------------
cmake_minimum_required(VERSION 3.1)

project(cmake_zmq_submodule)


# --------------------------------------------
# Language and Options Declaration
# --------------------------------------------

# CXX Standard 17
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# CXX compiler flags
set(BUILD_WARNINGS -Wall -Wextra -Wnon-virtual-dtor -Woverloaded-virtual -Wno-unknown-pragmas -Wconversion -Wmissing-declarations)


# --------------------------------------------
# Submodules
# --------------------------------------------

# Include the libzmq library as a subdirectory
add_subdirectory(extern/libzmq EXCLUDE_FROM_ALL)


# --------------------------------------------
# Target Executables and Libraries
# --------------------------------------------

# Declare the target executable and source files
add_executable(server exec/server.cpp)

# Declare the includes, libraries to link, and build options for the target
target_include_directories(server PUBLIC extern/cppzmq)
target_link_libraries(server PUBLIC libzmq-static)
target_compile_options(server PUBLIC ${BUILD_WARNINGS})

# Declare the target executable and source files
add_executable(client exec/client.cpp)

# Declare the includes, libraries to link, and build options for the target
target_include_directories(client PUBLIC extern/cppzmq)
target_link_libraries(client PUBLIC libzmq-static)
target_compile_options(client PUBLIC ${BUILD_WARNINGS})
