cmake_minimum_required(VERSION 3.6)
project(server2)

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY "${CMAKE_CURRENT_SOURCE_DIR}/bin")

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11 -pthread")

set(SOURCE_FILES
    src/connection.cpp
    src/io_service_pool.cpp
    src/main.cpp
    src/mime_types.cpp
    src/reply.cpp
    src/request_handler.cpp
    src/request_parser.cpp
    src/server.cpp)

include_directories(include)

link_libraries(boost_system boost_thread)

add_executable(server2 ${SOURCE_FILES})