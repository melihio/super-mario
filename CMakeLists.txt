cmake_minimum_required(VERSION 3.24)
project(Mario)

set(CMAKE_CXX_STANDARD 20)

include(FetchContent)

FetchContent_Declare(
        SFML
        GIT_REPOSITORY  https://github.com/SFML/SFML
        GIT_TAG         2.6.1
)
FetchContent_MakeAvailable(SFML)

FetchContent_Declare(
        fmt
        GIT_REPOSITORY  https://github.com/fmtlib/fmt
        GIT_TAG         10.2.1
)
FetchContent_MakeAvailable(fmt)


add_executable(Mario src/main.cpp src/Map.cpp src/Mario.cpp src/Map.cpp src/Game.cpp src/Coin.cpp src/Goomba.cpp src/Block.cpp src/Mushroom.cpp)

target_include_directories(Mario PRIVATE "${CMAKE_SOURCE_DIR/headers}")

target_link_libraries(Mario sfml-graphics)
target_link_libraries(Mario sfml-audio)
target_link_libraries(Mario fmt)
