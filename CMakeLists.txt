cmake_minimum_required(VERSION 2.8.3)
project(pcl_binvox)

# Use C++ 11
if(CMAKE_COMPILER_IS_GNUCXX)
  add_definitions("-std=c++11")
endif()

find_package(PCL REQUIRED)

include_directories(${PCL_INCLUDE_DIRS})
link_directories(${PCL_LIBRARY_DIRS})
add_definitions(${PCL_DEFINITIONS})

include_directories(${PCL_INCLUDE_DIRS})

link_directories(${LINK_DIRECTORIES} ${PCL_LIBRARY_DIRS})

add_executable(binvox2pcd src/binvox2pcd.cpp)
target_link_libraries(binvox2pcd ${PCL_LIBRARIES})

add_executable(pcd2binvox src/pcd2binvox.cpp)
target_link_libraries(pcd2binvox ${PCL_LIBRARIES})
