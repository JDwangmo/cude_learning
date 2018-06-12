cmake_minimum_required(VERSION 3.5)
project(untitled2 CXX CUDA)

set(CMAKE_CXX_STANDARD 11)
#set(CMAKE_MODULE_PATH "${CMAKE_CURRENT_SOURCE_DIR}/cmake")
#find_package(PythonLibs)
#include_directories(${PYTHON_INCLUDE_DIRS})
#add_library(untitled2 SHARED main.cpp cmake-build-debug/Rectangle.cc cmake-build-debug/Rectangle.h)
#target_link_libraries(untitled2 ${PYTHON_LIBRARIES})
find_package(CUDA REQUIRED)


message(STATUS "Find CUDA ${CUDA_LIBRARIES}")
message(STATUS "Find CUDA ${CUDA_INCLUDE_DIRS}")

include_directories(${CUDA_INCLUDE_DIRS})
#file(GLOB CUDA_FILES "src/" *.cu)
cuda_add_executable(
        untitled2
        main.cc
        src/add.cu
        )

target_link_libraries(untitled2 ${CUDA_LIBRARIES})

set_target_properties( untitled2
        PROPERTIES CUDA_SEPARABLE_COMPILATION ON)