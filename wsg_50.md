## 1. Package Summary ##

This package implements the driver in TCP/IP and CAN of the WSG 50 gripper.
Part of this driver is based on the original standalone driver for TCP developed by Weiss Robotics.

  * Autor: [Robotnik Automation](http://www.robotnik.eu/)
  * License: BSD
  * Source: svn http://wsg50-ros-pkg.googlecode.com/svn/trunk/wsg_50

## 2. Nodes ##

There are two nodes, one for each mode of connection: TCP and CAN.

### 2.1. wsg\_50\_tcp startup ###

  1. Connect the Ethernet cable and power on the gripper (24V).
  1. Establish a wired connection with fixed IP (e.g.: Method: MANUAL (without DHCP) IP: 192.168.1.XX, Netmask: 255.255.255.0, Gateway: 0.0.0.0).
  1. **rosrun wsg\_50 wsg\_50\_tcp** (This creates a socket that connects to the default IP gripper (192.168.1.20). This IP is configurable through the web interface, in this case must be changed the socket creation on the main.cpp source).

### 2.2. wsg\_50\_can startup ###

  1. Connect the CAN cable and power on the gripper (24V). Be sure that you have switched to CAN mode before, this can be done via TCP going to the section "Connection Mode" in the configuration site (192.168.1.20). You have to select: _Protocol: CAN. Speed: 500bps. Node number: 1._
  1. **roslaunch wsg\_50 wsg\_50\_can.launch** (This creates a socket that connects to the desired device (by default /dev/pcan32). This device is configurable via the launch file in the parameter "device".


## 3. Published topics ##

  * **wsg\_50\_x/status:** Publish the state of the gripper (fingers blocked, moving, position reached...) , opening width, programmed acceleration and force at 1Hz (configurable on the main loop).

_(Where **x** can be **tcp** or **can** depeding on the node that we have executed.)_

## 4. Services ##

  * **wsg\_50\_x/move:** Moves fingers to an absolute position at a specific velocity. Deprecated by the creation of the next service.
  * **wsg\_50\_x/move\_incrementally:** Moves fingers to a specific distance in a specific direction (open/close) regarding the anterior position.
  * **wsg\_50\_x/grasp:** Grasps an object of a specific width at a specific velocity. Normally used setting a zero width object and a low velocity.
  * **wsg\_50\_x/release:** Releases a grasped object opening the fingers to a indicated position.
  * **wsg\_50\_x/homing:** Moves fingers to home position (maximum opening).
  * **wsg\_50\_x/stop:** Stops a current action. **Not working yet.**
  * **wsg\_50\_x/ack:** Acknowledged an occurred error. **Not working yet.**
  * **wsg\_50\_x/set\_acceleration:** Set the acceleration with the gripper fingers moves.
  * **wsg\_50\_x/set\_force:** Set the force with the gripper grasp objects.

_(Where **x** can be **tcp** or **can** depeding on the node that we have executed.)_