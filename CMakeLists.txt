cmake_minimum_required(VERSION 2.8)
cmake_policy(SET CMP0015 NEW)
project(sqlite3)

if(UNIX)
set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -fPIC")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wall -DMATCH_MOCKUP -DSQLITE_HAS_CODEC -DSQLITE_USER_AUTHENTICATION")
else()
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -DMATCH_MOCKUP -DSQLITE_HAS_CODEC -DSQLITE_USER_AUTHENTICATION")
endif()

if(UNIX)
set(LIBRARY_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/lib)
#set(EXECUTABLE_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/bin)
else()
set(LIBRARY_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/out32)
#set(EXECUTABLE_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/bin)
endif()

include_directories(include)
#link_directories(${PROJECT_SOURCE_DIR}/lib)

set(SOURCE_FILES src/sqlite3secure.c)

add_library(sqlite3 ${SOURCE_FILES})