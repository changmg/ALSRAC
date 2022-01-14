# Set the minimum version of CMake that can be used
# To find the cmake version run
# $ cmake --version
cmake_minimum_required(VERSION 3.16)

# Set the project name
project(als)

# Add sub directories
add_subdirectory(abc)
add_subdirectory(espresso)
add_subdirectory(als)

# Add unit test
# include(googletest/googletest.cmake)
# fetch_googletest(
#     ${PROJECT_SOURCE_DIR}/googletest
#     ${PROJECT_BINARY_DIR}/googletest
# )
# 
# enable_testing()
# add_subdirectory(googletest)
