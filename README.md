# tmf882x_interfaces

This ROS 2 package houses the interface definitions for use with TMF882X sensors. Currently this is only one msg definition, TMF882XMeasure. This type holds all the data gathered from the sensor in a single iteration.

# Installation
Clone this repo to the `src` folder of your ROS 2 workspace, and run colcon build.

# Usage
If you are choosing to report only part of the data from the sensor, it is recommendd that you still use the TMF882XMeasure type, and leave any unreported fields blank. We don't want to create a new message type for every combination of fields that one might choose to report.

This is a standalone package for two reasons:
1. Portability - this message definition can live on many different machines and all be linked back to the same repository / package, without extra bloat.
2. In ROS 2 Iron, interface definitions can only be created in a CMake package, and it is inconvenient to build Python scripts in a CMake package (although it (can be done)[https://roboticsbackend.com/ros2-package-for-both-python-and-cpp-nodes/])