cmake_minimum_required(VERSION 3.16)

project(
    sds
    VERSION 2.0.0
    LANGUAGES C)

include(FetchContent)

FetchContent_Declare(
    mimalloc
    GIT_REPOSITORY https://github.com/microsoft/mimalloc.git
    GIT_TAG v3.0.1
)

FetchContent_MakeAvailable(mimalloc)

file(GLOB_RECURSE SDS_SOURCES ./*.c ./*.h)

add_library(sds STATIC sds.c)

target_link_libraries(sds PUBLIC mimalloc-static)

target_include_directories(sds PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})
