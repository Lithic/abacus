cmake_minimum_required (VERSION 3.1.0)

set(PROJECT_NAME abacus)

project(${PROJECT_NAME})
set(CMAKE_CXX_STANDARD 11)

# abacus
include_directories(include)
file(GLOB LIB_HEADERS "include/abacus/*.h")
file(GLOB LIB_SOURCES "src/abacus/*.cpp")
add_library(${PROJECT_NAME} ${LIB_HEADERS} ${LIB_SOURCES})
target_link_libraries(${PROJECT_NAME})

# abacus-test
include_directories(test/include)
file(GLOB TEST_HEADERS "test/include/abacus/*.h")
file(GLOB TEST_SOURCES "test/src/abacus/*.cpp")
set(TEST_SOURCES ${TEST_SOURCES} "test/src/main.cpp")
add_library(${PROJECT_NAME}-test ${TEST_HEADERS} ${TEST_SOURCES})
target_link_libraries(${PROJECT_NAME}-test ${PROJECT_NAME})
