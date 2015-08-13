cmake_minimum_required(VERSION 2.8.11)

project(simple_demo CXX)

if("${CMAKE_CXX_COMPILER_ID}" MATCHES "(GNU|Clang)")
    set(CMAKE_CXX_FLAGS "-std=c++11")
endif()

include(ExternalProject)

ExternalProject_Add(simple
	GIT_REPOSITORY https://github.com/oracle2025/cmake_simple_lib.git
	INSTALL_DIR ${PROJECT_BINARY_DIR}
	CMAKE_ARGS -DCMAKE_INSTALL_PREFIX:PATH=<INSTALL_DIR>)

#set(CMAKE_LIBRARY_PATH ${CMAKE_LIBRARY_PATH} ${PROJECT_BINARY_DIR}/simple-prefix/src/simple-build/lib/)

#find_library(SIMPLE_LIBS simple)
include_directories(${PROJECT_BINARY_DIR}/include)

add_subdirectory(src)

