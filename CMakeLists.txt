cmake_minimum_required(VERSION 3.0)
set(CMAKE_CXX_STANDARD 11)

include(cmake/HunterGate.cmake)

HunterGate(
    URL "https://github.com/Alexey01M/hunter/archive/v0.19.137.1.tar.gz"
    SHA1 "5119503aad2814e1aa69875f6ee8717430328698"
)

project(demo)

hunter_add_package(print)
find_package(print)

add_executable(demo ${CMAKE_CURRENT_SOURCE_DIR}/sources/demo.cpp)
target_link_libraries(demo print)

install(TARGETS demo RUNTIME DESTINATION bin)
