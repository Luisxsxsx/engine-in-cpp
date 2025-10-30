# Distributed under the OSI-approved BSD 3-Clause License.  See accompanying
# file Copyright.txt or https://cmake.org/licensing for details.

cmake_minimum_required(VERSION 3.22.1)

# We name the project and the target for the ExternalProject_Add() call
# to something that will highlight to the user what we are working on if
# something goes wrong and an error message is produced.

project(sdl2-populate NONE)



include(ExternalProject)
ExternalProject_Add(sdl2-populate
                     "UPDATE_DISCONNECTED" "False" "URL" "https://github.com/libsdl-org/SDL/releases/download/release-3.2.26/SDL3-3.2.26.zip" "URL_HASH" "SHA256=739356eef1192fff9d641c320a8f5ef4a10506b8927def4b9ceb764c7e947369"
                    SOURCE_DIR          "/home/lipe/enginge-in-cpp/build/_deps/sdl2-src"
                    BINARY_DIR          "/home/lipe/enginge-in-cpp/build/_deps/sdl2-build"
                    CONFIGURE_COMMAND   ""
                    BUILD_COMMAND       ""
                    INSTALL_COMMAND     ""
                    TEST_COMMAND        ""
                    USES_TERMINAL_DOWNLOAD  YES
                    USES_TERMINAL_UPDATE    YES
)


