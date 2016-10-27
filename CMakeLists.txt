# -- BEGIN LICENSE BLOCK ----------------------------------------------
# This program is free software licensed under the CDDL
# (COMMON DEVELOPMENT AND DISTRIBUTION LICENSE Version 1.0).
# You can find a copy of this license in LICENSE in the top
# directory of the source code.
#
# © Copyright 2016 FZI Forschungszentrum Informatik, Karlsruhe, Germany
# -- END LICENSE BLOCK ------------------------------------------------

#----------------------------------------------------------------------
# \file
#
# \author  Florian Kuhnt <kuhnt@fzi.de>
# \date    2016-09-15
#
#----------------------------------------------------------------------

cmake_minimum_required(VERSION 2.8.3)
project(fzi_sensor_msgs)

find_package(catkin REQUIRED COMPONENTS
  roscpp
  message_generation
  actionlib
  actionlib_msgs
  geometry_msgs
  sensor_msgs
  std_msgs
  fzi_geometry_msgs
  )

add_message_files(
  DIRECTORY msg
  FILES
  Object.msg
  ObjectArray.msg
  )

generate_messages(DEPENDENCIES
  actionlib_msgs
  geometry_msgs
  sensor_msgs
  std_msgs
  fzi_geometry_msgs
  )

catkin_package(
  CATKIN_DEPENDS actionlib_msgs message_runtime sensor_msgs std_msgs fzi_geometry_msgs
  )

include_directories(${catkin_INCLUDE_DIRS})