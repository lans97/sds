cmake_minimum_required(VERSION 3.15)

project(
    SDS
    VERSION 2.0.0
    LANGUAGES C)

find_package(mimalloc 2.1 REQUIRED)

file(GLOB_RECURSE SDS_SOURCES ./*.c ./*.h)

add_library(sds STATIC sds.c)
target_include_directories(sds INTERFACE ./)

target_link_libraries(sds PUBLIC mimalloc)
