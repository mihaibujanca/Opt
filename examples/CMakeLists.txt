cmake_minimum_required(VERSION 2.6.0)

project(ed_cpp)

set(CMAKE_BUILD_TYPE Debug)
#set(CMAKE_CXX_COMPILER clang++)
set(CMAKE_CXX_FLAGS "-std=c++11 -ldl")
set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} "${CMAKE_CURRENT_SOURCE_DIR}")
set(CMAKE_CXX_STANDARD 11)
set(TERRA_INCLUDE_DIRS /home/mihai/Projects/terra/include/terra)

find_package(CUDA REQUIRED)
list(APPEND CUDA_NVCC_FLAGS "-gencode;arch=compute_20,code=sm_20;-gencode;arch=compute_20,code=sm_21;-gencode;arch=compute_30,code=sm_30;-gencode;arch=compute_35,code=sm_35;-gencode;arch=compute_50,code=sm_50;-gencode;arch=compute_61,code=sm_61")
include_directories(${TERRA_INCLUDE_DIRS} ${CUDA_INCLUDE_DIRS} ../API/release/include external/mLib/include)

add_subdirectory(dynamicfusion)
#include (wildcard build/*.d)
