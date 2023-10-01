cmake_minimum_required(VERSION 3.16)
project(GuimaLang)

set(CMAKE_CXX_STANDARD 14)
set(BUILD_ARCH "-m64")
set(TARGET_64 ON)

# Import LLVM

find_package(LLVM REQUIRED CONFIG)

include_directories(${LLVM_INCLUDE_DIRS})
add_definitions(${LLVM_DEFINITIONS})
llvm_map_components_to_libnames(llvm_libs
    Analysis
    Core
    ExecutionEngine
    InstCombine
    Object
    OrcJIT
    RuntimeDyld
    ScalarOpts
    Support
    native)
