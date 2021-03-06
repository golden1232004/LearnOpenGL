cmake_minimum_required(VERSION 2.8)
project(SOIL)

set(EXECUTABLE_OUTPUT_PATH ${CMAKE_BINARY_DIR}/bin)
set(LIBRARY_OUTPUT_PATH ${CMAKE_BINARY_DIR}/bin)

include_directories(./include)
include_directories(./soil/src)
#find_library(SOIL_LIB NAME SOIL PATHS ./soil/lib)
#message(${SOIL_LIB})

file(GLOB soil_file ./soil/src/*.c)
add_library(SOIL SHARED ${soil_file})

set(EXT_LIB GL GLU GLEW m glfw)

file(GLOB f ./include/Shader.h)


add_executable(hello_triangle ./hello_triangle.cpp)
target_link_libraries(hello_triangle ${EXT_LIB} SOIL)

add_executable(hello_triangle2 ./hello_triangle2.cpp)
target_link_libraries(hello_triangle2 ${EXT_LIB} SOIL)

add_executable(hello_triangle_exercise1 ./hello_triangle_exercise1.cpp)
target_link_libraries(hello_triangle_exercise1 ${EXT_LIB} SOIL)

add_executable(hello_triangle_exercise2 ./hello_triangle_exercise2.cpp)
target_link_libraries(hello_triangle_exercise2 ${EXT_LIB} SOIL)

add_executable(hello_triangle_exercise3 ./hello_triangle_exercise3.cpp)
target_link_libraries(hello_triangle_exercise3 ${EXT_LIB} SOIL)

#########################################################################
add_executable(shaders-uniform ./shaders-uniform.cpp)
target_link_libraries(shaders-uniform ${EXT_LIB} SOIL)

add_executable(shaders-interpolated ./shaders-interpolated.cpp)
target_link_libraries(shaders-interpolated ${EXT_LIB} SOIL)

#########################################################################

add_executable(texture ./texture.cpp)
target_link_libraries(texture ${f} ${EXT_LIB} SOIL)

add_executable(texture_combined ./texture_combined.cpp)
target_link_libraries(texture_combined ${f} ${EXT_LIB} SOIL)

add_executable(texture_exercise3 ./texture_exercise3.cpp)
target_link_libraries(texture_exercise3 ${f} ${EXT_LIB} SOIL)

#########################################################################
add_executable(transform ./transform.cpp)
target_link_libraries(transform ${f} ${EXT_LIB} SOIL)

add_executable(transform_exercise ./transform_exercise.cpp)
target_link_libraries(transform_exercise ${f} ${EXT_LIB} SOIL)

#########################################################################

add_executable(coordinate_systems ./coordinate_systems.cpp)
target_link_libraries(coordinate_systems ${f} ${EXT_LIB} SOIL)

add_executable(coordinate_systems_with_depth ./coordinate_systems_with_depth.cpp)
target_link_libraries(coordinate_systems_with_depth ${f} ${EXT_LIB} SOIL)

add_executable(coordinate_systems_multiple_objects ./coordinate_systems_multiple_objects.cpp)
target_link_libraries(coordinate_systems_multiple_objects ${f} ${EXT_LIB} SOIL)
