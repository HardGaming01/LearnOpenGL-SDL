cmake_minimum_required(VERSION 3.3)

project(GLFWTutorial)

set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} "${CMAKE_SOURCE_DIR}/cmake")

if(MSVC)
  # Modify this path to point to your libraries if you are using microsoft compiler
  set(CMAKE_PREFIX_PATH "C:/CXXDev/vc++")
endif(MSVC)

find_package(SDL2 REQUIRED)
find_package(GLM REQUIRED)

include_directories(include)
include_directories(${SDL2_INCLUDE_DIR})

add_subdirectory(src)
