cmake_minimum_required(VERSION 3.0.2)
project(sky_mission)

find_package(catkin REQUIRED COMPONENTS
  geometry_msgs
  mavros
  roscpp
  rospy
  std_msgs
  sensor_msgs
  mavros_msgs
  roslaunch
)

include_directories(
# include
  ${catkin_INCLUDE_DIRS}
)

catkin_python_setup()
catkin_package()

install(PROGRAMS 
  scripts/*
  DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
)

## Mark other files for installation (e.g. launch and bag files, etc.)
# install(FILES
#   # myfile1
#   # myfile2
#   DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
# )