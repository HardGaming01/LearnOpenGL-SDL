cmake_minimum_required(VERSION 3.3)

project(LearnOpenGL-SDL)

set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} "${CMAKE_SOURCE_DIR}/cmake")

find_package(SDL2 CONFIG REQUIRED)
find_package(GLM CONFIG REQUIRED)

if (MSVC)
    # For vcpkg, include path is not provided directly
    find_path(SDL2_INCLUDE_DIR SDL2/SDL.h)
endif ()

include_directories(include)
include_directories(${SDL2_INCLUDE_DIR})
include_directories(${GLM_INCLUDE_DIR})

add_subdirectory(src)
