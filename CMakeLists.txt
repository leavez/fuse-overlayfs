cmake_minimum_required(VERSION 3.0)
project(fuse-overlayfs)

file(GLOB SRC_FILES ${CMAKE_CURRENT_SOURCE_DIR}/*.c)
file(GLOB HEADER ${CMAKE_CURRENT_SOURCE_DIR}/*.h)

source_group("src" FILES ${SRC_FILES} ${HEADER})

include_directories(${CMAKE_CURRENT_SOURCE_DIR})

add_executable(fuse-overlayfs ${SRC_FILES} ${HEADER})


