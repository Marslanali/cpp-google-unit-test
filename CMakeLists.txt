cmake_minimum_required(VERSION 3.5.1)
project(unit-test-google)
set(CMAKE_CXX_STANDARD 11)
#set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11 -pthread ")

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=gnu++11")

#############################################
# Unit tests

# Locate GTest
find_package(GTest REQUIRED)
include_directories(${GTEST_INCLUDE_DIRS})

# Link runTests with what we want to test and the GTest and pthread library
add_executable(unit-test ${PROJECT_SOURCE_DIR}/sqrt_test.cpp)
target_link_libraries(unit-test ${GTEST_LIBRARIES} pthread)

