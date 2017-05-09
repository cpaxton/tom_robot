cmake_minimum_required(VERSION 2.8.0)
project(tum_ics_lacquey_gripper_msgs)

find_package(catkin REQUIRED COMPONENTS 
  std_msgs
  geometry_msgs
  sensor_msgs
  message_generation
)

add_message_files(
    DIRECTORY msg
    FILES
	  GripperState.msg
)


generate_messages(
  DEPENDENCIES
  std_msgs
  geometry_msgs
  sensor_msgs
)

catkin_package(
 #INCLUDE_DIRS include
 CATKIN_DEPENDS std_msgs geometry_msgs sensor_msgs message_runtime 
)

#install(DIRECTORY include/${PROJECT_NAME}/
#  DESTINATION ${CATKIN_PACKAGE_INCLUDE_DESTINATION}
#)


