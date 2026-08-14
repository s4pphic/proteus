# Proteus central CMakeFile
# (C) s4pphic and proteus contributors
#
# NOTE: This idea of a main "do-all" CMakeLists is temporary.
#       Once the project is larger and is organized, this will
#       break apart into several smaller compact files.
#       - s4pphic (08-14-2026)

cmake_minimum_required(VERSION 3.28)
project(
    Proteus
    VERSION 0.1
    LANGUAGES C CXX
)

file(GLOB_RECURSE PROTEUS_SOURCES CONFIGURE_DEPENDS
    "${CMAKE_SOURCE_DIR}/Source/*.cpp"
    "${CMAKE_SOURCE_DIR}/Source/*.c"
)

file(GLOB_RECURSE PROTEUS_HEADERS CONFIGURE_DEPENDS
    "${CMAKE_SOURCE_DIR}/Include/Proteus/*.h"
    "${CMAKE_SOURCE_DIR}/Include/Proteus/*.hpp"
)

add_library(Proteus STATIC
    ${PROTEUS_SOURCES}
    ${PROTEUS_HEADERS}
)

# The literal bare minimum just to show that something builds, as this expands
# it'll be broken apart to separate modules. Keep an eye out for a cmake dir
# in the near future.