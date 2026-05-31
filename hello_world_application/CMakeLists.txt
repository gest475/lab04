cmake_minimum_required(VERSION 3.5)
project(hello_world)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_executable(hello_world hello_world.cpp)
target_link_libraries(hello_world formatter_ex)

install(TARGETS hello_world RUNTIME DESTINATION bin)
