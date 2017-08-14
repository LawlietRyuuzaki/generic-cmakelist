cmake_minimum_required(VERSION 3.0)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")
set(PROJECTNAME "Game")


project(${PROJECTNAME})

file(GLOB_RECURSE
source
./src/main.cpp
)

file(GLOB_RECURSE
headers
./src/headers/*
)

add_executable(${PROJECTNAME} ${source} ${headers})

set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} "./CMake/")
find_package(SFML REQUIRED graphics window system)
if (SFML_FOUND)
    include_directories(${SFML_INCLUDE_DIR})
    target_link_libraries(${PROJECTNAME} ${SFML_LIBRARIES})
endif(SFML_FOUND)
