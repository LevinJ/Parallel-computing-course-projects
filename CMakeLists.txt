############################################################################
# <summary> CMakeLists.txt for OpenCV and CUDA. </summary>
# <date>    2012-02-07          </date>
# <author>  Quan Tran Minh. edit by Johannes Kast, Michael Sarahan </author>
# <email>   quantm@unist.ac.kr  kast.jo@googlemail.com msarahan@gmail.com</email>
############################################################################

cmake_minimum_required(VERSION 2.6 FATAL_ERROR)
project(cs344)
message(STATUS "CMAKE_MODULE_PATH:${CMAKE_MODULE_PATH}")

set(OpenCV_DIR  /home/levin/projects/toolboxes/opencv/build/debug)
find_package(OpenCV 2.4  REQUIRED)
find_package(CUDA REQUIRED)

link_libraries(${OpenCV_LIBS} )



set (EXECUTABLE_OUTPUT_PATH "${CMAKE_SOURCE_DIR}/build/")

IF(NOT CMAKE_BUILD_TYPE)
  SET(CMAKE_BUILD_TYPE Debug CACHE STRING
      "Choose the type of build, options are: None Debug Release RelWithDebInfo MinSizeRel."
      FORCE)
ENDIF(NOT CMAKE_BUILD_TYPE)

  # add debugging to CUDA NVCC flags.  For NVidia's NSight tools.
  set(CUDA_NVCC_FLAGS_DEBUG ${CUDA_NVCC_FLAGS_DEBUG} "-G -g -O0")

  #add_subdirectory (./Problem\ Sets/Problem\ Set\ 1)
  add_subdirectory (./Problem\ Sets/Problem\ Set\ 2)
  #add_subdirectory (HW3)
  #add_subdirectory (HW4)
  #add_subdirectory (HW5)
  #add_subdirectory (HW6)

