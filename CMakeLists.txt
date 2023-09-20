cmake_minimum_required(VERSION 3.25.0)
project(
    tre
    VERSION 0.8.0
    DESCRIPTION "The approximate regex matching library and agrep command line tool."
    LANGUAGES C)

#set(CMAKE_CXX_STANDARD 17)
#set(CMAKE_CXX_STANDARD_REQUIRED ON)

#message(STATUS "CMAKE_CXX_STANDARD: ${CMAKE_CXX_STANDARD}")

# Only do these if this is the main project, and not if it is included through add_subdirectory
if(CMAKE_PROJECT_NAME STREQUAL PROJECT_NAME)
    include(CTest)
endif()

add_subdirectory(lib)
# add_subdirectory(src)
