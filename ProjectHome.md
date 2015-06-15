# WSG 50 ROS PACKAGE #

## 1. Package Summary ##

Driver for ROS to control the [WSG 50 gripper](http://www.weiss-robotics.de/gripper-systems/gripper-modules/universal-gripper-wsg-50.html), both in simulated and real version (using TCP or CAN protocol).
Part of this driver is based on the original standalone driver for TCP developed by Weiss Robotics.

  * Autor: [Robotnik Automation](http://www.robotnik.eu/)
  * License: BSD
  * Source: svn http://wsg50-ros-pkg.googlecode.com/svn/trunk/

## 2. Supported Hardware ##

This package should work with [WSG 50 grippers](http://www.weiss-robotics.de/gripper-systems/gripper-modules/universal-gripper-wsg-50.html). In the CAN node, this driver assumes that you are using a PEAK USB-CAN converter, otherwise, it won't work.



## 3. Packages ##

### 3.1 wsg\_50 ###

[This package](http://code.google.com/p/wsg50-ros-pkg/wiki/wsg_50) implements the driver for the real gripper. You can control it via TCP/IP or CAN.

### 3.2 wsg\_50\_simulation ###

[This package](http://code.google.com/p/wsg50-ros-pkg/wiki/wsg_50_simulation) implements the Gazebo gripper simulation. It contains the meshes and URDF files for the visualization and two programs, one for fake the real gripper services and other to teleoperate it with the keyboard.


### 3.3 wsg\_50\_common ###

[This package](http://code.google.com/p/wsg50-ros-pkg/wiki/wsg_50_common) contains the definitions of the msg's and srv's used by the real and simulated gripper.


## 4. Examples of use ##

![http://i48.tinypic.com/33ykrkj.jpg](http://i48.tinypic.com/33ykrkj.jpg)

