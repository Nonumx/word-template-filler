cmake_minimum_required(VERSION 3.25)
project(word-tf)

set(CMAKE_CXX_STANDARD 20)

file(GLOB SRC_FILES
        ${PROJECT_SOURCE_DIR}/*.h
        ${PROJECT_SOURCE_DIR}/*.cpp)

set(THIRD_PARTY_DIR ${CMAKE_SOURCE_DIR}/third_party)

set(THIRD_PARTY_ZIP
        ${THIRD_PARTY_DIR}/zip/zip.h
        ${THIRD_PARTY_DIR}/zip/zip.c
        ${THIRD_PARTY_DIR}/zip/miniz.h)

set(THIRD_PARTY_PUGIXML
        ${THIRD_PARTY_DIR}/pugixml/pugixml.hpp
        ${THIRD_PARTY_DIR}/pugixml/pugixml.cpp
        ${THIRD_PARTY_DIR}/pugixml/pugiconfig.hpp)

add_library(${PROJECT_NAME} SHARED ${SRC_FILES} ${THIRD_PARTY_ZIP} ${THIRD_PARTY_PUGIXML})

set_target_properties(${PROJECT_NAME} PROPERTIES
    RUNTIME_OUTPUT_DIRECTORY ${CMAKE_SOURCE_DIR}/bin
    ARCHIVE_OUTPUT_DIRECTORY ${CMAKE_SOURCE_DIR}/lib
    DEBUG_POSTFIX "d"
)