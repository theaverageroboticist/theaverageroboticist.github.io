+++
title = 'Jetson Yolo'
date = 2024-04-23T20:15:02+02:00
draft = false
+++

## Setting up Azure Kinect with Jetson

Asumming that you have ubuntu 20 running on your jetson. Unfotunately at the time of writhing this the SDK is not available for ubuntu 20, but the SDK for 18 can be made to work on 20.

- First download the repo config package with `curl -sSL -O https://packages.microsoft.com/config/ubuntu/18.04/packages-microsoft-prod.deb`.
- Install the config package `sudo dpkg -i packages-microsoft-prod.deb`.
- Delete it after installation `rm packages-microsoft-prod.deb`.
- Open the file `etc/apt/sources.list.d/microsoft-prod.list` with your favourite editor.

Change the repository Linux repository path 
```
deb [arch=arm64] https://packages.microsoft.com/ubuntu/18.04/multiarch/prod bionic main
```

- Update the apt repository `sudo apt update`
- Install the package with `sudo apt install libk4a1.4 libk4a1.4-dev k4a-tools`
- Test the installation by launching `k4aviewer`
- Copy the [script](https://github.com/microsoft/Azure-Kinect-Sensor-SDK/blob/develop/scripts/99-k4a.rules) into `/etc/udev/rules.d/` to avoid using root all the time.

## Installing the ros2 foxy driver for Azure Kinect


- source the underlay `source /opt/ros/foxy/setup.bash`
- Clone the repo from the foxy branch `git clone https://github.com/microsoft/Azure_Kinect_ROS_Driver.git -b foxy-devel`
- Install the dependencies `pip3 install xacro ; sudo apt install ros-foxy-joint-state-publisher`
- `cd Azure_Kinect_ROS_Driver`
- Build the package `colcon build` 
- Source the overlay `source install/setup.bash`
- Launch with `ros2 launch azure_kinect_ros_driver driver.launch.py`
- Open `rviz2` in another terminal to view the topics that are published.
- Refer the [usage guide](https://github.com/microsoft/Azure_Kinect_ROS_Driver/blob/foxy-devel/docs/usage.md) for configuration.
