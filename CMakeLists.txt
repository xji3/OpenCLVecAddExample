cmake_minimum_required(VERSION 3.14)
project(OrkRidgeOpenCLVecAdd LANGUAGES CXX CUDA)

set(CMAKE_CXX_STANDARD 14)

find_package(OpenCL REQUIRED)
if(OpenCL_FOUND)
    message(STATUS "OpenCL Includes: ${OpenCL_INCLUDE_DIRS}")
    message(STATUS "OpenCL Libraries: ${OpenCL_LIBRARIES}")
endif(OpenCL_FOUND)


include_directories(
        ${OpenCL_LIBRARIES}
        ${PROJECT_SOURCE_DIR}
        ${OpenCL_INCLUDE_DIRS}
        ${OpenCL_INCLUDE_DIRS}/Headers
)

add_executable(OrkRidgeOpenCLVecAdd main.cpp)
target_link_libraries(OrkRidgeOpenCLVecAdd OpenCL::OpenCL)