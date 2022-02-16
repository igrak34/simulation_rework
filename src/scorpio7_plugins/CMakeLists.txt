cmake_minimum_required(VERSION 3.0.2)
project(scorpio7_plugins)

find_package(catkin REQUIRED COMPONENTS
  gazebo_ros
  roscpp
)

find_package(gazebo REQUIRED)

catkin_package(
  LIBRARIES
    scorpio7_gazebo_differential_plugin
)

link_directories(${GAZEBO_LIBRARY_DIRS})

include_directories(${catkin_INCLUDE_DIRS} ${GAZEBO_INCLUDE_DIRS})

add_library(scorpio7_gazebo_differential_plugin 
  src/differential_plugin.cpp
)
target_link_libraries(scorpio7_gazebo_differential_plugin ${catkin_LIBRARIES} ${GAZEBO_LIBRARIES})