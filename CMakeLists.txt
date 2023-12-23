cmake_minimum_required(VERSION 3.0)
project(fuse-overlayfs)

file(GLOB SRC_LIST ${CMAKE_CURRENT_SOURCE_DIR}/*.c)
add_executable(fuse-overlayfs ${SRC_LIST})

