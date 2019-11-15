﻿cmake_minimum_required (VERSION 3.8)

project ("BS_Engine" VERSION 0.0.1 LANGUAGES CXX)

# debug
if ("${CMAKE_BUILD_TYPE}" STREQUAL "DEBUG")
    add_definitions (-D_DEBUG)
endif ()

# architecture
if ( CMAKE_SIZEOF_VOID_P EQUAL 8 )
set(ARCH_DIR "x64")
else()
set(ARCH_DIR "x86")
endif()

add_subdirectory ("engine")