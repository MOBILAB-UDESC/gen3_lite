cmake_minimum_required(VERSION 3.22)
project(gen3_lite_moveit_config)

find_package(ament_cmake REQUIRED)

install(DIRECTORY config DESTINATION share/${PROJECT_NAME})

ament_package()