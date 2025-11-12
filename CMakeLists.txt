cmake_minimum_required(VERSION 3.15)
project(My2DEngine)

set(CMAKE_CXX_STANDARD 23)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/build)
# Cria diretório 'build' automaticamente se não existir
if(NOT EXISTS ${CMAKE_BINARY_DIR})
    file(MAKE_DIRECTORY ${CMAKE_BINARY_DIR})
endif()

add_subdirectory(libs)
add_subdirectory(src)