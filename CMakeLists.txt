cmake_minimum_required(VERSION 3.0)

project(ProjectName)

file(GLOB_RECURSE
source
./src/*
)

file(GLOB_RECURSE
headers
./headers/*
)

add_executable(ProjectName ${source} ${headers})
