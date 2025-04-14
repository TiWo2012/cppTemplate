cmake_minimum_required(VERSION 3.15)

# Project name and version
project(projectName VERSION 1.0)

# Set C++ standard
set(CMAKE_CXX_STANDARD 23)
set(CMAKE_CXX_STANDARD_REQUIRED True)

# Add executable
add_executable(executableName src/main.cc)

# example of how to download raylib and build it
# Include FetchContent module
# include(FetchContent)

# Fetch raylib
# FetchContent_Declare(
#     raylib
#     GIT_REPOSITORY https://github.com/raysan5/raylib.git
#     GIT_TAG 4.5.0 # Use the latest stable version
# )
#
# Build raylib
# FetchContent_MakeAvailable(raylib)

# Link raylib to the executable
target_link_libraries(executableName PRIVATE raylib)

# Add compiler options for raylib
if (CMAKE_SYSTEM_NAME STREQUAL "Linux")
    target_link_libraries(executableName PRIVATE m) # Link math library on Linux
endif()
