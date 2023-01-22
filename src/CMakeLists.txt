CMAKE_MINIMUM_REQUIRED(VERSION 3.25)

project(CVLib C CXX)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

set(THIRD_PARTY_DIR ${CMAKE_CURRENT_SOURCE_DIR}/third_party CACHE PATH "Path to Third Party folder")
set(Eigen3_INCLUDE_DIR ${THIRD_PARTY_DIR}/Eigen/ CACHE PATH "Path to Eigen source folder")


add_executable(main main.cpp)
target_include_directories(main PUBLIC ${Eigen3_INCLUDE_DIR})
# add_subdirectory(cvlib)
# add_subdirectory(tests)