cmake_minimum_required(VERSION 3.10)
project(hw1)

set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED True)

add_subdirectory(${CMAKE_SOURCE_DIR}/../third_party/googletest
        ${CMAKE_BINARY_DIR}/third_party/googletest-build)

add_executable(hw1
        src/main.cpp
        src/Vector.cpp
        src/unit_test.cpp)

# include 路径，确保 gmock/gmock.h 能被找到
target_include_directories(hw1 PRIVATE ${PROJECT_SOURCE_DIR}/include)
target_include_directories(hw1 PRIVATE ${CMAKE_SOURCE_DIR}/../third_party/googletest/googlemock/include)
target_include_directories(hw1 PRIVATE ${CMAKE_SOURCE_DIR}/../third_party/googletest/googletest/include)

target_link_libraries(hw1
        gtest
        gtest_main
        )

