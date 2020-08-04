cmake_minimum_required(VERSION 3.14)

project(GLEW)

add_library(
    GLEW
    SHARED
    src/glew.c
)

target_compile_definitions(GLEW PUBLIC GLEW_BUILD)
target_include_directories(GLEW PRIVATE include)

add_library(
    GLEWs
    STATIC
    src/glew.c
)

set_target_properties(GLEWs PROPERTIES OUTPUT_NAME "GLEW")
target_compile_definitions(GLEWs PUBLIC GLEW_STATIC)
target_include_directories(GLEWs PRIVATE include)
target_link_libraries(GLEW "OpenGL32.lib")