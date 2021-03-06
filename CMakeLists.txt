cmake_minimum_required(VERSION 3.7.2)
project(clang_devel_clion)

set(CMAKE_CXX_STANDARD 11)

file(GLOB project_include
        llvm-include/llvm/Pass.h

        llvm-include/llvm/IR/*.h
        llvm-include/llvm/IR/*.def

        llvm-include/llvm/Support/*.h
        llvm-include/llvm/Support/*.def

        llvm-include/llvm/IRReader/*.h
        llvm-include/llvm/IRReader/*.def

        llvm-include/llvm/Transforms/*.h
        llvm-include/llvm/Transforms/*.def

        llvm-include/llvm/Bitcode/*.h
        llvm-include/llvm/Bitcode/*.def
        )

set(SOURCE_FILES
        ${project_include}

        func-pointer/LLVMAssignment.cpp
        func-pointer/log.cpp
        func-pointer/log.h
        )

include_directories(func-pointer)
include_directories(llvm-include)

add_executable(clang_devel_clion ${SOURCE_FILES})