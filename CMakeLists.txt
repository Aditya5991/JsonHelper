cmake_minimum_required(VERSION 3.10)
project(JsonHelper VERSION 1.0)

# Set the output directory for the binaries based on architecture and build type
if(CMAKE_SIZEOF_VOID_P EQUAL 8)
    set(ARCHITECTURE "x64")
else()
    set(ARCHITECTURE "x86")
endif()

# Set the output directory for the JsonHelper library
set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${CMAKE_SOURCE_DIR}/bin/${ARCHITECTURE}/${CMAKE_BUILD_TYPE})
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_SOURCE_DIR}/bin/${ARCHITECTURE}/${CMAKE_BUILD_TYPE})
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_SOURCE_DIR}/bin/${ARCHITECTURE}/${CMAKE_BUILD_TYPE})

# Add the source files of JsonHelper
file(GLOB_RECURSE JSON_HELPER_SOURCES src/*.cpp)

# Add the executable target for JsonHelper
add_library(JsonHelper ${JSON_HELPER_SOURCES})

