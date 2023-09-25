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

option(SFML_BUILD_EXAMPLES  "Build SFML examples"   OFF)
option(SFML_BUILD_DOC       "Build SFML doc"        OFF)
option(SFML_BUILD_AUDIO     "Build SFML Audio"      OFF)
option(SFML_BUILD_GRAPHICS  "Build SFML Graphics"   ON)
option(SFML_BUILD_WINDOW    "Build SFML Window"     ON)
option(SFML_BUILD_NETWORK   "Build SFML Network"    OFF)

option(SFML_INSTALL_PKGCONFIG_FILES "Install pkg-config files for sfml" OFF)

FetchContent_Declare(
    sfml
    GIT_REPOSITORY  https://github.com/sfml/sfml.git
    GIT_TAG         2.6.x
)
message(STATUS "Download sfml from Github and configure...")
FetchContent_MakeAvailable(sfml)

message(STATUS "in sub-directory src/")
add_subdirectory(src)
