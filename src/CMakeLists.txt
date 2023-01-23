

# Set the output folder where your program will be created
# set(CMAKE_BINARY_DIR ${CMAKE_SOURCE_DIR}/bin)
# set(EXECUTABLE_OUTPUT_PATH ${CMAKE_BINARY_DIR})
# set(LIBRARY_OUTPUT_PATH ${CMAKE_BINARY_DIR})



add_executable(main main.cpp)
target_include_directories(main PUBLIC ${EIGEN_INCLUDE_DIRS})


# add_subdirectory(cvlib)
# add_subdirectory(tests)