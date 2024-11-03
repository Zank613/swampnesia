cmake_minimum_required(VERSION 3.0)
project(Swampnesia)

# Set the path to your Raylib include and lib directories
set(RAYLIB_INCLUDE_DIR "${CMAKE_SOURCE_DIR}/raylib5/include")
set(RAYLIB_LIB_DIR "${CMAKE_SOURCE_DIR}/raylib5/lib")

# Add the Raylib header files
include_directories(
    ${RAYLIB_INCLUDE_DIR},
    ${CMAKE_SOURCE_DIR}/include)

# Find the Raylib library
find_library(RAYLIB_LIB raylib HINTS ${RAYLIB_LIB_DIR})

# Add executable
add_executable(Swampnesia src/main.c)

# Link Raylib and necessary system libraries
target_link_libraries(Swampnesia ${RAYLIB_LIB} opengl32 gdi32 winmm)
