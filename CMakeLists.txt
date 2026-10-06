cmake_minimum_required(VERSION 3.24)
project(tacklebox_engine LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

include(FetchContent)

# SFML
set(SFML_BUILD_GRAPHICS OFF)
set(SFML_BUILD_AUDIO OFF)
set(SFML_BUILD_NETWORK OFF)
FetchContent_Declare(SFML
    GIT_REPOSITORY https://github.com/SFML/SFML.git
    GIT_TAG 3.1.0
    GIT_SHALLOW ON
)
FetchContent_MakeAvailable(SFML)

# GLM
FetchContent_Declare(glm
    GIT_REPOSITORY https://github.com/g-truc/glm.git
    GIT_TAG 1.0.3
    GIT_SHALLOW ON
)
FetchContent_MakeAvailable(glm)

add_library(tacklebox_engine
    src/engine.cpp
)

target_include_directories(tacklebox_engine PUBLIC include)
target_link_libraries(tacklebox_engine PRIVATE SFML::Window SFML::System)
target_link_libraries(tacklebox_engine PUBLIC glm::glm)
