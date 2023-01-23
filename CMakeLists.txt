CMAKE_MINIMUM_REQUIRED(VERSION 3.25)

project(CVLib C CXX)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)


# ==============================================================================
# Additional cmake find modules
# ==============================================================================
set(CMAKE_MODULE_PATH
  ${CMAKE_MODULE_PATH} ${CMAKE_CURRENT_SOURCE_DIR}/cmakeFindModules)


# # TODO: convert to function later
# message(STATUS ">>>> START OF PRINT DEBUG <<<<")
# message(STATUS "${CMAKE_CURRENT_SOURCE_DIR}")
# message(STATUS ">>>> END OF PRINT DEBUG <<<<")

# # TODO: convert to function later
# message(STATUS ">>>> START OF PRINT DEBUG <<<<")
# message(STATUS "${CMAKE_MODULE_PATH}")
# message(STATUS ">>>> END OF PRINT DEBUG <<<<")


find_package(Eigen3 QUIET)
if (NOT Eigen3_FOUND)
  set(EIGEN_INCLUDE_DIR_HINTS ${CMAKE_CURRENT_SOURCE_DIR}/extern/eigen)
  set(OpenMVG_USE_INTERNAL_EIGEN ON)
  find_package(Eigen QUIET)
else()
  set(EIGEN_INCLUDE_DIRS ${EIGEN3_INCLUDE_DIR})
endif()

# Set the output folder where your program will be created
# set(CMAKE_BINARY_DIR ${CMAKE_SOURCE_DIR}/bin)
# set(EXECUTABLE_OUTPUT_PATH ${CMAKE_BINARY_DIR})
# set(LIBRARY_OUTPUT_PATH ${CMAKE_BINARY_DIR})


add_subdirectory(src)
# target_include_directories(main PUBLIC ${Eigen3_INCLUDE_DIR})
# add_subdirectory(cvlib)
# add_subdirectory(tests)