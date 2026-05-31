cmake_minimum_required(VERSION 3.5)
project(solver_lib)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_library(solver_lib STATIC ${CMAKE_CURRENT_SOURCE_DIR}/solver.cpp)
target_include_directories(solver_lib PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})

install(TARGETS solver_lib ARCHIVE DESTINATION lib)
install(FILES solver.h DESTINATION include)
