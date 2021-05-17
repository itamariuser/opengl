# cmake_minimum_required(VERSION <specify CMake version here>)
cmake_minimum_required(VERSION 3.3)
project(untitled)

set(CMAKE_CXX_STANDARD 14)

add_executable(untitled main.cpp)

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${PROJECT_BINARY_DIR})

add_library(glad ${CMAKE_SOURCE_DIR}/glad/include/glad/glad.h ${CMAKE_SOURCE_DIR}/glad/src/glad.c)
add_library(glew ${CMAKE_SOURCE_DIR}/glew/include/GL/glew.h ${CMAKE_SOURCE_DIR}/glew/src/glew.c)
include_directories(
        ${OPENGL_INCLUDE_DIR}
        glfw-3.3.4.bin.WIN64/include
        glfw-3.3.4.bin.WIN64/lib-mingw-w64
        glad/include
        glm/
        glew/include/
)

find_library(GLFW glfw3 HINTS glfw-3.3.4.bin.WIN64/lib-mingw-w64)
find_library(GLFW glfw3 HINTS glfw-3.3.4.bin.WIN64/lib-mingw-w64)
find_library(GLFW glew32 HINTS glew-2.1.0/bin/Release/x64)
target_include_directories(glad PUBLIC glad/include)
#target_include_directories(glew PUBLIC glew-2.1.0/bin/Release/x64)
target_link_libraries(untitled ${OPENGL_gl_LIBRARY} ${GLFW} glad glew)