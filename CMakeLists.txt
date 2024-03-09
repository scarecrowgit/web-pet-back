cmake_minimum_required(VERSION 3.10)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

set(MYSQL_CONNECTOR_CPP_INCLUDE_DIR ${CMAKE_CURRENT_SOURCE_DIR}/include/mysql-concpp/include())
set(MYSQL_CONNECTOR_CPP_JDBC_DIR ${CMAKE_CURRENT_SOURCE_DIR}/include/mysql-concpp/include/jdbc())
set(MYSQL_CONNECTOR_CPP_MYSQLX_DIR ${CMAKE_CURRENT_SOURCE_DIR}/include/mysql-concpp/include/mysqlx())
set(MYSQL_CONNECTOR_CPP_LIB_DIR  ${CMAKE_CURRENT_SOURCE_DIR}/include/mysql-concpp/lib64())
set(MYSQL_CONNECTOR_CPP_INCLUDE_DIR /usr/local/mysql-connector-c++-8.3.0/include)
set(MYSQL_CONNECTOR_CPP_LIB_DIR /usr/local/mysql-connector-c++-8.3.0/lib64)


set(MYSQL_SERVER_INCLUDE_DIR /usr/local/mysql-8.3.0-macos14-arm64/include/mysql)
set(MYSQL_SERVER_LIB_DIR /usr/local/mysql-8.3.0-macos14-arm64/lib)

set(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -L${MYSQL_CONNECTOR_CPP_LIB_DIR}")
find_library(MYSQL_LIBRARIES mysqlcppconn8 HINTS ${MYSQL_CONNECTOR_CPP_LIB_DIR})


set(MYSQL_LIBRARIES libmysqlcppconn8.dylib)

include_directories(${MYSQL_CONNECTOR_CPP_INCLUDE_DIR} ${MYSQL_CONNECTOR_CPP_JDBC_DIR} ${MYSQL_CONNECTOR_CPP_MYSQLX_DIR} ${MYSQL_SERVER_INCLUDE_DIR})

project(web-pet-back VERSION 0.1)
add_executable(web-pet-back controller.cpp)

target_include_directories(web-pet-back PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/include())

target_link_libraries(web-pet-back ${MYSQL_LIBRARIES})
