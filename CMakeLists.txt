cmake_minimum_required(VERSION 3.24)
project(tacklebox_engine LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_library(tacklebox_engine
    src/engine.cpp
)

target_include_directories(tacklebox_engine PUBLIC include)
