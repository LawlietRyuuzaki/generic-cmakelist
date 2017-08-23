cmake_minimum_required(VERSION 3.0)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")
set(PROJECTNAME "Random")

project(${PROJECTNAME})

file(GLOB_RECURSE
source
${CMAKE_SOURCE_DIR}/src/*
)

file(GLOB_RECURSE
headers
${CMAKE_SOURCE_DIR}/headers/*
)

add_executable(${PROJECTNAME} ${source} ${headers})

set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} "${CMAKE_SOURCE_DIR}/CMake")

#<Windows>
#set(SFML_ROOT "C:/SFML-2.4.2")
#set(SFML_INCLUDE_DIR "C:/SFML-2.4.2/include")
#set(SFML_LIBRARY_DIR "C:/SFML-2.4.2/lib")
#</Windows>

find_package(SFML REQUIRED graphics window system)
if (SFML_FOUND)
    include_directories(${SFML_INCLUDE_DIR})
    target_link_libraries(${PROJECTNAME} ${SFML_LIBRARIES})
endif(SFML_FOUND)
