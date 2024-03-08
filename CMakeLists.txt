cmake_minimum_required(VERSION 3.22)
project(WebPetBack)

add_executable(WebPetBack viewmodel.cpp)

target_include_directories(WebPetBack PRIVATE "${CMAKE_SOURCE_DIR}/include")
target_include_directories(WebPetBack PRIVATE "${CMAKE_SOURCE_DIR}/include/boost")
target_include_directories(WebPetBack PRIVATE "${CMAKE_SOURCE_DIR}/include/mysql-connector-c++-8.3.0")
target_include_directories(WebPetBack PRIVATE "${CMAKE_SOURCE_DIR}/include/mysql-connector-c++-8.3.0/include/jdbc")

set_property(TARGET WebPetBack PROPERTY CXX_STANDARD 20)
