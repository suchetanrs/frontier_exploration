cmake_minimum_required(VERSION 3.5)
project(exploration_msgs)

set_directory_properties(PROPERTIES COMPILE_OPTIONS "-std=c++14;-Wall;-Werror")

find_package(ament_cmake REQUIRED)
find_package(rosidl_default_generators REQUIRED)
find_package(geometry_msgs REQUIRED)

rosidl_generate_interfaces(${PROJECT_NAME}
"action/Explore.action"
"srv/SetPolygon.srv"
DEPENDENCIES builtin_interfaces geometry_msgs
)

ament_export_dependencies(rosidl_default_runtime)

ament_package()