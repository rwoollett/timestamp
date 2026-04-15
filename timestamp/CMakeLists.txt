cmake_minimum_required(VERSION 3.16)

add_library(Timestamp INTERFACE)

target_include_directories(Timestamp INTERFACE
    ${CMAKE_CURRENT_SOURCE_DIR}/include
)