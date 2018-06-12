cmake_minimum_required(VERSION 3.5)
project(untitled2 CXX)

set(CMAKE_CXX_STANDARD 11)

find_package(CUDA REQUIRED)

message(STATUS "Find CUDA ${CUDA_LIBRARIES}")
message(STATUS "Find CUDA ${CUDA_INCLUDE_DIRS}")

include_directories(${CUDA_INCLUDE_DIRS})

cuda_add_executable(
        untitled2
        main.cc
        src/add.cu
        )

target_link_libraries(untitled2 ${CUDA_LIBRARIES})

