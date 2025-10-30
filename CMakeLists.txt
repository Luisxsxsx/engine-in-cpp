cmake_minimum_required(VERSION 3.15)

project(My2DEngine VERSION 0.1.0 LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Cria diretório 'build' automaticamente se não existir
if(NOT EXISTS ${CMAKE_BINARY_DIR})
    file(MAKE_DIRECTORY ${CMAKE_BINARY_DIR})
endif()

# 🔥 MÓDULO FETCHCONTENT - PARA BAIXAR DEPENDÊNCIAS AUTOMATICAMENTE
include(FetchContent)

if(CMAKE_BUILD_TYPE STREQUAL "Debug")
    set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -g -O0 -Wall")
else()
    set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -O2 -Wall")
endif()

add_subdirectory(external)  # 🔥 PRIMEIRO: Compila dependências
add_subdirectory(src)