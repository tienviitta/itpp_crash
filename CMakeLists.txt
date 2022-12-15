cmake_minimum_required(VERSION 3.4...3.18)
project(itpp_crash LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# find_package(armadillo REQUIRED)
find_path(ITPP_INC itpp)
message(STATUS "ITPP_INC: [${ITPP_INC}]")
find_library(ITPP_LIB itpp)
message(STATUS "ITPP_LIB: [${ITPP_LIB}]")

# link_directories(${ITPP_LIB})
add_executable(itpp_crash main.cpp)
include_directories(${ITPP_INC})
target_link_libraries(itpp_crash ${ITPP_LIB})
