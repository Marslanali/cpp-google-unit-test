cmake_minimum_required(VERSION 3.5.1)
project(unit-test-google)
set(CMAKE_CXX_STANDARD 14)
#set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11 -pthread ")
#set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=gnu++11")

############################################################
# Check CMake version, Compiler, and OS.
############################################################
message(STATUS "CMake version   : " ${CMAKE_SYSTEM_VERSION})
message(STATUS "Compiler        : " ${CMAKE_CXX_COMPILER})
message(STATUS "Operating System: " ${CMAKE_SYSTEM})

############################################################
# Find GTest package
############################################################
if (WIN32)
    # for Windows operating system in general
    ADD_SUBDIRECTORY(googletest)
    enable_testing()
endif ()

if (UNIX)
    # for Linux
    find_package(GTest REQUIRED)
endif (UNIX)

############################################################
# Target Include Directories
############################################################
if (WIN32)
    include_directories(${gtest_SOURCE_DIR}/include ${gtest_SOURCE_DIR})
endif ()

if (UNIX)
    include_directories(${GTEST_INCLUDE_DIRS})
endif ()

############################################################
# Create a executable for UTest
############################################################
add_executable(UTest ${PROJECT_SOURCE_DIR}/src/unit-test.cpp)

############################################################
# Target Link Libaries
############################################################
if (WIN32)
    # link with arithmetic_circuits_library
    target_link_libraries(UTest
            PUBLIC
            gtest gtest_main pthread
            )
    add_test(UTest UTest)
endif ()

if (UNIX)
    # link with arithmetic_circuits_library
    target_link_libraries(UTest
            PUBLIC
            ${GTEST_LIBRARIES} pthread
            )
endif ()
