cmake_minimum_required(VERSION 3.16)

project(hello_world_cpp LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

# src 配下の .cpp をすべて収集
file(GLOB SRC_FILES CONFIGURE_DEPENDS
    ${CMAKE_SOURCE_DIR}/src/*.cpp
)

add_executable(hello_world ${SRC_FILES})

target_include_directories(hello_world PRIVATE
    ${CMAKE_SOURCE_DIR}/src
)

# install ターゲットを定義
install(TARGETS hello_world DESTINATION bin)
