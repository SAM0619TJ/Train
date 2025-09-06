cmake_minimum_required(VERSION 3.10)
project(Train)

set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED True)


find_package(GTest REQUIRED)
include_directories(${PROJECT_SOURCE_DIR}/include)
add_subdirectory( ${CMAKE_SOURCE_DIR}/../third_party/googletest
        ${CMAKE_BINARY_DIR}/third_party/googletest-build)
add_executable(Train
        src/main.cpp
        src/Vector.cpp
        src/unit_test.cpp)
target_link_libraries(Train
        gtest
        gtest_main
)
