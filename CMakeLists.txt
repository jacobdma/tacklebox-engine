cmake_minimum_required(VERSION 3.24)
project(tacklebox_engine LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

include(FetchContent)

set(SFML_BUILD_GRAPHICS OFF)
set(SFML_BUILD_AUDIO OFF)
set(SFML_BUILD_NETWORK OFF)
FetchContent_Declare(SFML
    GIT_REPOSITORY https://github.com/SFML/SFML.git
    GIT_TAG 3.1.0
    GIT_SHALLOW ON
)
FetchContent_MakeAvailable(SFML)

add_library(tacklebox_engine
    src/engine.cpp
)

target_include_directories(tacklebox_engine PUBLIC include)
target_link_libraries(tacklebox_engine PRIVATE SFML::Window SFML::System)
