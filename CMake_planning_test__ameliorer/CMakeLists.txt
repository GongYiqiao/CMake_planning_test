cmake_minimum_required(VERSION 4.0.0)
project(planning)
set(CMAKE_CXX_STANDARD 17)

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${PROJECT_SOURCE_DIR}/bin)#
#CMAKE_LIBRARY_OUTPUT_DIRECTORT  linux

aux_source_directory(${PROJECT_SOURCE_DIR}/src SRC_LISTS)

add_library(common SHARED ${SRC_LISTS})

target_include_directories(common PUBLIC ${PROJECT_SOURCE_DIR}/include)

add_executable(planning_main main.cpp)

target_include_directories(planning_main PUBLIC ${PROJECT_SOURCE_DIR}/include)

target_link_libraries(planning_main PUBLIC common)
