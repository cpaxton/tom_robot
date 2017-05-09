##############################################################################
# CMake
##############################################################################

cmake_minimum_required(VERSION 2.8.0)
project(tum_ics_msgs)

set( CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -w -Wno-cpp" )

##############################################################################
# Catkin
##############################################################################

find_package(catkin REQUIRED COMPONENTS 
  actionlib
  actionlib_msgs
  std_msgs
  geometry_msgs
  sensor_msgs
  message_generation
)

##############################################################################
# Messages, Services and Actions
##############################################################################
add_message_files(
   DIRECTORY msg
   FILES 
  VisualInfo.msg
  )



## Generate added messages and services with any dependencies listed here
generate_messages(
  DEPENDENCIES  
  actionlib_msgs
  std_msgs
  geometry_msgs
  sensor_msgs
)



###################################
## catkin specific configuration ##
###################################
## The catkin_package macro generates cmake config files for your package
## Declare things to be passed to dependent projects
## INCLUDE_DIRS: uncomment this if you package contains header files
## LIBRARIES: libraries you create in this project that dependent projects also need
## CATKIN_DEPENDS: catkin_packages dependent projects also need
## DEPENDS: system dependencies of this project that dependent projects also need
catkin_package(
 INCLUDE_DIRS 
 CATKIN_DEPENDS actionlib actionlib_msgs std_msgs message_runtime geometry_msgs sensor_msgs
)



include_directories(
  ${catkin_INCLUDE_DIRS}
  ${roscpp_INCLUDE_DIRS}
)


install(DIRECTORY include/${PROJECT_NAME}/
  DESTINATION ${CATKIN_PACKAGE_INCLUDE_DESTINATION}
)

