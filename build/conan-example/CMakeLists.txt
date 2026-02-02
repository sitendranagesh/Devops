cmake_minimum_required(VERSION 3.16)
project(conan_demo)

add_library(mathutils STATIC math_utils.cpp)

find_package(fmt REQUIRED)
target_include_directories(mathutils
    PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}
)

add_executable(app main.cpp)

target_link_libraries(app
    PRIVATE
        mathutils
        fmt::fmt
)




