# Set the minimum version of CMake that can be used
# To find the cmake version run
# $ cmake --version
cmake_minimum_required(VERSION 3.16)

# Set the project name
project(alsrac)

# Set top directory
set(TOP_DIR ${PROJECT_SOURCE_DIR}/..)

# Collect source files
aux_source_directory(${PROJECT_SOURCE_DIR}/src sources)

# Add include paths
include_directories(${TOP_DIR}/abc/src)
include_directories(${TOP_DIR}/espresso/src)
include_directories(${PROJECT_SOURCE_DIR}/src)

# Add definitions
add_definitions(-DLIN64 -g -Wall -O3 -std=c++2a)

# Set output path
set(EXECUTABLE_OUTPUT_PATH ${TOP_DIR})

# # Add an static library with the above sources
# add_library(${PROJECT_NAME} STATIC ${sources})
# target_link_libraries(${PROJECT_NAME} libabc espresso -lm -ldl -rdynamic -lreadline -ltermcap -lpthread -lstdc++ -lrt -lstdc++fs)

# Add an executable
add_executable(alsrac.out ${sources})
target_link_libraries(alsrac.out libabc espresso -lm -ldl -rdynamic -lreadline -ltermcap -lpthread -lstdc++ -lrt -lstdc++fs)
