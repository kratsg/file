cmake_minimum_required (VERSION 3.15)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_MACOSX_RPATH 1)

project(file VERSION 0.0.1 DESCRIPTION "open source implementation of the file(1) command that ships with most free operating systems")
#add_subdirectory(doc)
#add_subdirectory(magic)
#add_subdirectory(python)
add_subdirectory(src)
