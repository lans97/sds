cmake_minimum_required(VERSION 3.15)

project(
    SDS
    VERSION 2.0.0
    LANGUAGES C)

file(GLOB_RECURSE SDS_SOURCES ./*.c ./*.h)

add_library(sds INTERFACE ${SDS_SOURCES})
target_include_directories(sds INTERFACE ./)

