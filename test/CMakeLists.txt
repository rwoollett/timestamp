cmake_minimum_required(VERSION 3.16)

add_executable(LoadTest
  load.cpp
)

target_link_libraries(
  LoadTest PRIVATE
  Timestamp
)

get_target_property(dirs Timestamp INTERFACE_INCLUDE_DIRECTORIES)
message(STATUS "Include dirs: ${dirs}")
