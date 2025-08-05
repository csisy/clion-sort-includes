cmake_minimum_required(VERSION 4.0.2)
project(Example LANGUAGES CXX)

add_library(MyLib STATIC)

target_sources(MyLib
        PUBLIC
        FILE_SET HEADERS BASE_DIRS includes FILES
        includes/MyLib/A.h
        includes/MyLib/B.h

        PRIVATE
        src/B.cpp
)
