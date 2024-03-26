cmake_minimum_required(VERSION 3.25)
project(word-tf)

file(GLOB SRC_FILES
        ${PROJECT_SOURCE_DIR}/*.h
        ${PROJECT_SOURCE_DIR}/*.cpp)

add_library(${PROJECT_NAME} SHARED ${SRC_FILES})