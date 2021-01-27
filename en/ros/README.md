# Robotics using ROS

[ROS](http://www.ros.org/) (Robot Operating System) is a general purpose robotics library that can be used with PX4 for [offboard control](../ros/mavros_offboard.md).
It uses the [MAVROS](../ros/mavros_installation.md) node to communicate with PX4 running on hardware or using the [Gazebo Simulator](../simulation/ros_interface.md).

This section contains topics about using ROS for offboard control with PX4.

:::tip
ROS is only officially supported on Linux platforms.
:::

# Robotics using ROS 2

[ROS 2](https://index.ros.org/doc/ros2/) is the newest version of ROS 2, adapting most of the changes that occurred in ROS (1) over the last years and bringing the best of ROS (1),
while at the same time improving some things that weren't so go good.

The interface between ROS 2 and PX4 is possible through the [*microRTPS* bridge](../middleware/micrortps.md), a bridge established between the PX4 internals, using the uORB Pub/Sub
architecture, and correspondent IDL types, that are used to generate, not only serialization and deserialization code, but also the ROS 2 messages and typesupport, required to use
the equivalents of the uORB messages in the ROS 2 development workflows and nodes.

:::note
The usage of the *microRTPS* bridge to interface with PX4 using ROS 2 implies that the user/developer has enough understanding of the PX4 internals so it is able to interact with them
properly. In contrast with ROS 1 and the usage of MAVROS, this is required because, while MAVROS offers a layer of abstraction on top of MAVLink, which by itself has already its own
micro-services, on the contrary, that layer of abstraction does not exist with this bridge, besides some helper functions to do frame transformations and unit conversions. In the other hand,
this will be made more accessible as soon as it is made available some ROS 2 API and examples that allow interaction with the PX4 internals - this is current not available, but is
currently on the plans of the development team.
:::

For an explanation on how the bridge works, and for some examples, please check [this section](../ros/ros2_comm.md).
W
## Installation

The easiest way to setup PX4 simulation with ROS (on Ubuntu Linux) is to use the standard installation script that can be found at [Development Environment on Linux > Gazebo with ROS](../dev_setup/dev_env_linux_ubuntu.md#rosgazebo).
The script installs everything you need: PX4, ROS, the Gazebo simulator, and [MAVROS](../ros/mavros_installation.md).

:::note
If you just need to install ROS then follow the [ROS Melodic installation instructions](http://wiki.ros.org/melodic/Installation) for your platform.
:::


## External Resources

- [XTDrone](https://github.com/robin-shaun/XTDrone/blob/master/README.en.md) - ROS + PX4 simulation environment for computer vision.
  The [XTDrone Manual](https://www.yuque.com/xtdrone/manual_en) has everything you need to get started!
