cmake_minimum_required(VERSION 3.25)

project(snake-game
    VERSION 1.0
    LANGUAGES CXX
    DESCRIPTION "Snake game with SFML"
)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED)
set(CMAKE_INCLUDE_CURRENT_DIR OFF)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_SOURCE_DIR}/bin)

include(FetchContent)

FetchContent_Declare(
    sfml
    GIT_REPOSITORY  https://github.com/sfml/sfml.git
    GIT_TAG         2.6.x
)
message(STATUS "Download sfml from github...")
FetchContent_MakeAvailable(sfml)

add_subdirectory(src)
