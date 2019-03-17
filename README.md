Unmaned Aerial Vehicles in JdeRobot with ROS
========

The new Hardware Abstraction Layer (HAL) for working in robotic applications for Unmanned Aerial Vehicles (UAVs) in JdeRobot is based on using ROS/Gazebo and:

* [PX4](https://px4.io/) as main flight control software. 
* [MavROS](http://wiki.ros.org/mavros) as MAVLink-based communication node between ROS and the PX4 flight stack. It also provides an UDP bridge for MAVLink Ground Control Stations

# Installation instructions

Please follow the next steps to install the complete JdeRobot UAVs HAL:

## ROS Kinetic and Gazebo 7

ROS must be already installed before continuing. Please follow [the official instructions](http://wiki.ros.org/kinetic/Installation/Ubuntu) to install ROS Kinetic (that includes Gazebo 7 by default) in Ubuntu 16.04 (Xenial)

## MavROS

Install MavROS package and its required dependencies following [these installation instructions](https://github.com/mavlink/mavros/blob/master/mavros/README.md#installation). Binary installation (deb packages) is recommended.

## PX4 SITL

Download the last PX4 Firmware from its Github repository:

```sh
git clone https://github.com/PX4/Firmware.git 
```

*To be completed*

```sh
cd <Firmware_clone>
make px4_sitl_default gazebo
source ~/catkin_ws/devel/setup.bash    // (optional)
source Tools/setup_gazebo.bash $(pwd) $(pwd)/build/px4_sitl_default
export ROS_PACKAGE_PATH=$ROS_PACKAGE_PATH:$(pwd)
export ROS_PACKAGE_PATH=$ROS_PACKAGE_PATH:$(pwd)/Tools/sitl_gazebo
```

*To be completed: modifications to add front camera*

## PX4 SITL + MavROS launch files

Default launch file for PX4 SITL + MavROS + Gazebo (included in the MavROS package):

```sh
roslaunch px4 mavros_posix_sitl.launch 
```

*Update vehicle options (to be completed):*

```sh
roslaunch px4 mavros_px4sitl_camera.launch vehicle:=solo
roslaunch px4 mavros_px4sitl_camera.launch vehicle:=iris model_name:=iris_fpv_cam
roslaunch px4 mavros_px4sitl_camera.launch vehicle:=solo model_name:=solo
```

## Hardware compatibility

This HAL is compatible with any UAVs including a Pixhawk flight controller or any other board flashed with the PX4 stack. 

* A list of compatible boards can be found [here](https://docs.px4.io/en/flight_controller/#documented-boards)
* Some complete UAVs run PX4 "out of the box". There is a list [here](https://docs.px4.io/en/complete_vehicles/) 


