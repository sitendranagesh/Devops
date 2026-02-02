add_library(mathutils STATIC math_utils.cpp)
add_executable(app main.cpp)
target_link_libraries(app PRIVATE mathutils)
