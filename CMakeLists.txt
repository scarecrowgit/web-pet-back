cmake_minimum_required(VERSION 3.22)
project(WebPetBack)

add_executable(WebPetBack viewmodel.cpp)

target_include_directories(WebPetBack PRIVATE "${CMAKE_SOURCE_DIR}/include")
target_include_directories(WebPetBack PRIVATE "${CMAKE_SOURCE_DIR}/include/boost")

set_property(TARGET WebPetBack PROPERTY CXX_STANDARD 20)
