cmake_minimum_required(VERSION 2.8)
project(SOIL)

set(EXECUTABLE_OUTPUT_PATH ${CMAKE_BINARY_DIR}/bin)
set(LIBRARY_OUTPUT_PATH ${CMAKE_BINARY_DIR}/bin)

include_directories(./)
include_directories(./soil/src)
#find_library(SOIL_LIB NAME SOIL PATHS ./soil/lib)
#message(${SOIL_LIB})

file(GLOB soil_file ./soil/src/*.c)
add_library(SOIL SHARED ${soil_file})

set(EXT_LIB GL GLU GLEW m glfw)

file(GLOB f ./Shader.h)


add_executable(hello_triangle ./hello_triangle.cpp)
target_link_libraries(hello_triangle ${f} ${EXT_LIB} SOIL)

add_executable(hello_triangle2 ./hello_triangle2.cpp)
target_link_libraries(hello_triangle2 ${f} ${EXT_LIB} SOIL)


add_executable(texture ./texture.cpp)
target_link_libraries(texture ${f} ${EXT_LIB} SOIL)