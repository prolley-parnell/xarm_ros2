cmake_minimum_required(VERSION 3.5)
project(realsense_gazebo_plugin)

# Default to C++14
if(NOT CMAKE_CXX_STANDARD)
  set(CMAKE_CXX_STANDARD 14)
endif()
if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  # we dont use add_compile_options with pedantic in message packages
  # because the Python C extensions dont comply with it
  set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wall -Wextra -Wpedantic -Wno-inconsistent-missing-override")
endif()

#set(FastRTPS_INCLUDE_DIR /opt/ros/foxy/include) 
set(FastRTPS_INCLUDE_DIR /opt/ros/humble/include) 
set(FastRTPS_LIBRARY_RELEASE /opt/ros/humble/lib/libfastrtps.so)
# Load catkin and all dependencies required for this package
find_package(ament_cmake REQUIRED)
# find_package(gz-cmake3 REQUIRED)
# find_package(rclcpp REQUIRED)
# #find_package(gazebo_ros REQUIRED)
# find_package(ros_gz_sim REQUIRED)

# find_package(image_transport REQUIRED)
# find_package(camera_info_manager REQUIRED)
# find_package(sensor_msgs REQUIRED)
# find_package(gz-plugin2 REQUIRED COMPONENTS all)
# set(GZ_PLUGIN_VER ${gz-plugin2_VERSION_MAJOR})
# find_package(gz-common5 REQUIRED COMPONENTS profiler)
# set(GZ_COMMON_VER ${gz-common5_VERSION_MAJOR})
# find_package(gz-sensors8 REQUIRED)
# set(GZ_SENSOR_VER ${gz-sensors8_VERSION_MAJOR})
# find_package(gz-physics7 REQUIRED all)
# set(GZ_PHYSICS_VER ${gz-physics7_VERSION_MAJOR})

# # Harmonic
# if("$ENV{GZ_VERSION}" STREQUAL "harmonic")
#   find_package(gz-sim8 REQUIRED)
#   set(GZ_SIM_VER ${gz-sim8_VERSION_MAJOR})
#   message(STATUS "Compiling against Gazebo Harmonic")
# # Default to Garden
# else()
#   find_package(gz-sim7 REQUIRED)
#   set(GZ_SIM_VER ${gz-sim7_VERSION_MAJOR})
#   message(STATUS "Compiling against Gazebo Garden")
# endif()

# #set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} ${GAZEBO_CXX_FLAGS}")

# set( dependencies
#     rclcpp
#     #gazebo_ros
#     ros_gz_sim
#     image_transport
#     camera_info_manager
#     sensor_msgs
#     gz-sim${GZ_SIM_VER}
# )

# include_directories(
#     SYSTEM
#     include
#     ${SDFORMAT-INCLUDE_DIRS}
#     ${GZ-COMMON_INCLUDE_DIRS}
#     ${GZ-SIM_INCLUDE_DIRS}
#     ${GZ-SENSORS_INCLUDE_DIRS}
# )

# link_directories(${GAZEBO_LIBRARY_DIRS})

# add_library(
#     ${PROJECT_NAME} SHARED
#     src/RealSensePlugin.cpp
#     src/gazebo_ros_realsense.cpp
#     )

# ament_target_dependencies(${PROJECT_NAME} ${dependencies})
# target_link_libraries(${PROJECT_NAME} ${GAZEBO_LIBRARIES})

# install(TARGETS ${PROJECT_NAME} 
#   ARCHIVE DESTINATION lib
#   LIBRARY DESTINATION lib
#   RUNTIME DESTINATION bin
# )

# install(DIRECTORY include/
#   DESTINATION include/
# )

# if(BUILD_TESTING)
#   find_package(ament_lint_auto REQUIRED)
#   ament_lint_auto_find_test_dependencies()
# endif()

# ament_export_include_directories(include)
# ament_export_libraries(${PROJECT_NAME})
ament_package()
