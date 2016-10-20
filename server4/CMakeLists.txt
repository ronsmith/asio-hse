cmake_minimum_required(VERSION 3.6)
project(server4)

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY "${CMAKE_CURRENT_SOURCE_DIR}/bin")

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11 -pthread")

set(SOURCE_FILES
        include/header.hpp
        include/mime_types.hpp
    include/reply.hpp
    include/request.hpp
        include/request_parser.hpp
    include/server.hpp
        src/main.cpp
    src/mime_types.cpp
    src/reply.cpp
        src/request_parser.cpp
    src/server.cpp src/file_handler.cpp include/file_handler.hpp)

include_directories(include)

link_libraries(boost_system boost_thread)

add_executable(server4 ${SOURCE_FILES})