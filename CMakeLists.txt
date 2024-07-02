cmake_minimum_required(VERSION 3.0.2)
project(four_wheel_vehicle)

find_package(catkin REQUIRED COMPONENTS
  roscpp
  geometry_msgs
  gazebo_msgs
  gazebo_plugins
  gazebo_ros
  gazebo_ros_control
)

## Generate messages in the 'msg' folder
# add_message_files(
#   FILES
#   Message1.msg
#   Message2.msg
# )

## Generate services in the 'srv' folder
# add_service_files(
#   FILES
#   Service1.srv
#   Service2.srv
# )

## Generate actions in the 'action' folder
# add_action_files(
#   FILES
#   Action1.action
#   Action2.action
# )

## Generate added messages and services with any dependencies listed here
# generate_messages(
#   DEPENDENCIES
#   gazebo_msgs
# )



## Generate dynamic reconfigure parameters in the 'cfg' folder
# generate_dynamic_reconfigure_options(
#   cfg/DynReconf1.cfg
#   cfg/DynReconf2.cfg
# )


catkin_package(
#  INCLUDE_DIRS include
#  LIBRARIES four_wheel_vehicle
#  CATKIN_DEPENDS gazebo_msgs gazebo_plugins gazebo_ros gazebo_ros_control
#  DEPENDS system_lib
)



## Your package locations should be listed before other locations
include_directories(
# include
  ${catkin_INCLUDE_DIRS}
)

add_executable(teleop_twist_keyboard src/teleop_twist_keyboard.cpp)
target_link_libraries(teleop_twist_keyboard ${catkin_LIBRARIES})