cmake_minimum_required(VERSION 3.5)

project(demoOpen62541)

set (EXECUTABLE_OUTPUT_PATH  ${PROJECT_SOURCE_DIR}/bin)

add_definitions(-std=c99)

include_directories(${PROJECT_SOURCE_DIR}/open62541)

find_library(OPEN62541_LIB libopen62541.a HINTS ${PROJECT_SOURCE_DIR}/open62541/bin)

add_executable(server ${PROJECT_SOURCE_DIR}/src/server.c)
target_link_libraries(server ${OPEN62541_LIB})

add_executable(client ${PROJECT_SOURCE_DIR}/src/client.c)
target_link_libraries(client ${OPEN62541_LIB})

