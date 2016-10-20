cmake_minimum_required(VERSION 3.6)
project(server3)

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY "${CMAKE_CURRENT_SOURCE_DIR}/bin")

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11  -pthread")

set(SOURCE_FILES
        include/connection.hpp
        include/header.hpp
        include/mime_types.hpp
        include/reply.hpp
        include/request.hpp
        include/request_handler.hpp
        include/request_parser.hpp
        include/server.hpp
        src/connection.cpp
        src/main.cpp
        src/mime_types.cpp
        src/reply.cpp
        src/request_handler.cpp
        src/request_parser.cpp
        src/server.cpp)

include_directories(include)

link_libraries(boost_system boost_thread)

add_executable(server3 ${SOURCE_FILES})