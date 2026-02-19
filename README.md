# GEN3 LITE

<p align="center">
  <img src="https://raw.githubusercontent.com/MOBILAB-UDESC/gen3_lite/main/doc/resources/gen3_lite.png" alt="gen3_lite" width="180"/>
</p>

## Description
ROS 2 description and simulation package for the **Kinova Gen3 Lite** manipulator with MoveIt 2 integration.

**Note:** This package is a submodule of the [arms](https://github.com/MOBILAB-UDESC/arms.git) meta-package.

## ROS 2 info
|Ubuntu|ROS 2 Distro|Gazebo Version|
|:----:|:---------------:|:------------:|
|[24.04](https://ubuntu.com/blog/tag/ubuntu-24-04-lts)|[Jazzy](https://docs.ros.org/en/jazzy/index.html)|[Harmonic](https://gazebosim.org/docs/harmonic/getstarted/)|


## Cloning and building
``` cli
mkdir ~/arms_ws && cd ~/arms_ws
git clone https://github.com/MOBILAB-UDESC/arms.git src
cd src
git submodule update --init gen3_lite kinova_2f_lite
cd ..
rosdep install --from-paths src --ignore-src -r -y
colcon build
source install/setup.bash
```

## Configuration
Compatible gripper:
- **kinova_2f_lite** (default).

## Simulation
#### Launch gazebo world
``` cli
ros2 launch arms_bringup arm_world_launch.py world_name:=playground
```

#### Spawn the robot
``` cli
ros2 launch arms_bringup arm.launch.py use_sim_time:=true arm:=gen3_lite gripper:=kinova_2f_lite use_camera:=true rviz:=false
```

#### Launch moveit
``` cli
ros2 launch arms_bringup arm_moveit_launch.py use_sim_time:=true arm:=gen3_lite gripper:=kinova_2f_lite rviz:=true
```