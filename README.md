Unmaned Aerial Vehicles in JdeRobot with ROS
========

The new Hardware Abstraction Layer (HAL) for working in robotic applications for Unmanned Aerial Vehicles (UAVs) in JdeRobot is based on using ROS/Gazebo and:

* [PX4](https://px4.io/) as main flight control software. 
* [MavROS](http://wiki.ros.org/mavros) as MAVLink-based communication node between ROS and the PX4 flight stack. It also provides an UDP bridge for MAVLink Ground Control Stations

# Installation steps for PX4 SITL 

Please follow these steps to install the complete UAVs HAL.

## ROS Kinetic and Gazebo 7

ROS Kinetic (that includes Gazebo 7 by default) must be installed first. Please follow  

## PX4 SITL

Download the last PX4 Firmware from its Github repository:


```sh
$  git clone https://github.com/PX4/Firmware.git 
```

Build the code

## Hardware compatibility

This HAL is compatible with any UAVs including a Pixhawk flight controller or any other board flashed with the PX4 stack. 

* A list of compatible boards can be found [here](https://docs.px4.io/en/flight_controller/#documented-boards)
* Some complete UAVs run PX4 "out of the box". There is a list [here](https://docs.px4.io/en/complete_vehicles/) 


