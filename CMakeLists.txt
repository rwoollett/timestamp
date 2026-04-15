cmake_minimum_required(VERSION 3.16)
project(
  TimestampProject VERSION 1.0
  DESCRIPTION "Timestamp header only"
  LANGUAGES CXX C
)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)
set(CMAKE_C_FLAGS_TSAN "-O1 -g -fsanitize=thread -fno-omit-frame-pointer")
set(CMAKE_CXX_FLAGS_TSAN "-O1 -g -fsanitize=thread -fno-omit-frame-pointer")
set(CMAKE_EXE_LINKER_FLAGS_TSAN "-fsanitize=thread")
set(CMAKE_SHARED_LINKER_FLAGS_TSAN "-fsanitize=thread")

# set everything up for c++ 20 features
set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_subdirectory(timestamp)

option(BUILD_TIMESTAMP_TESTS "Build tests" OFF)

if(BUILD_TIMESTAMP_TESTS)

  add_subdirectory(test)

endif()

