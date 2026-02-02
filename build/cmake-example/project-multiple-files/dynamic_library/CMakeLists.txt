add_library(mathutils SHARED math_utils.cpp)
add_executable(app main.cpp)
target_link_libraries(app PRIVATE mathutils)
