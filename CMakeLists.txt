cmake_minimum_required(VERSION 3.5)
project(fuse-overlayfs)

file(GLOB SRCs ${CMAKE_CURRENT_SOURCE_DIR}/*.c)
file(GLOB HEADERs ${CMAKE_CURRENT_SOURCE_DIR}/*.h)
file(GLOB LIB_SRCs ${CMAKE_CURRENT_SOURCE_DIR}/lib/*.c)
file(GLOB LIB_HEADERs ${CMAKE_CURRENT_SOURCE_DIR}/lib/*.h)
set(README ${CMAKE_CURRENT_SOURCE_DIR}/README.md)

source_group("src" FILES ${SRCs} ${HEADERs} )
source_group("src/lib" FILES ${LIB_SRCs} ${LIB_HEADERs})
source_group("" FILES ${README})

#include_directories("/usr/local/include/fuse")

set(MAIN fuse-overlayfs)
add_executable(${MAIN} ${SRCs} ${HEADERs} ${LIB_SRCs} ${LIB_HEADERs}  ${README})
target_include_directories(${MAIN} PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/lib "/usr/local/include/fuse")
target_link_directories(${MAIN} PRIVATE "/usr/local/lib")
target_link_libraries(${MAIN} PRIVATE osxfuse pthread)


