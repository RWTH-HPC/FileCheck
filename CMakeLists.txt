
cmake_minimum_required(VERSION 3.9)
project(FileCheck
        VERSION 15.0.6
        DESCRIPTION "A standalone build of LLVM FileCheck")

set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# For configured files
include_directories(${CMAKE_CURRENT_BINARY_DIR}/include)
add_definitions(-DHAVE_UNISTD_H)

# Naming it just FileCheck leads to collisions with the LLVM cmake module
add_executable(MUST_FileCheck FileCheck.cpp)
set_target_properties(MUST_FileCheck
        PROPERTIES
        OUTPUT_NAME FileCheck
        CXX_STANDARD 14
        CXX_STANDARD_REQUIRED ON)

target_include_directories(MUST_FileCheck PRIVATE include)
target_link_libraries(MUST_FileCheck PRIVATE MUST_LLVMFileCheck)

add_subdirectory(lib)
