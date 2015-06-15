## 1. Package Summary ##

This package implements the necessary for the simulation in Gazebo of the WSG 50 gripper (URDF'S, meshes, controllers and programs).


  * Autor: [Robotnik Automation](http://www.robotnik.eu/)
  * License: BSD
  * Source: svn http://wsg50-ros-pkg.googlecode.com/svn/trunk/wsg_50_simulation

## 2. Nodes ##

### 2.1. wsg\_50\_sim\_driver ###

This node is executed automatically in the launch file and provide services that fake the WSG 50 gripper originals.

### 2.2. wsg\_50\_keyboard\_teleop ###

This node provide the necessary to teleoperate the gripper via keyboard. We can open the fingers pressing **"W"** and we can close them by pressing **"S"**.


## 3. Published topics ##

  * **/wsg\_50\_gl/state:** Publish the state of the gripper left controller, implemented using a simple **Joint Position Controller** from the package **robot\_mechanism\_controllers**.
  * **/wsg\_50\_gr/state:** Publish the state of the gripper right.

## 4. Services ##

  * **wsg\_50\_sim/move:** Moves fingers to an absolute position [0.0 - 110.0]
  * **/wsg\_50/move\_incrementally:** Service based on the previous that allow to move the gripper with the "robotnik\_powerball\_pad".
  * **wsg\_50\_sim/homing:** Moves fingers to home position (minimum opening).
  * **/wsg\_50/grasp:** Moves fingers to 0.0 (same that home, faked service to allow to use with the "robotnik\_powerball\_pad".



## 5. Startup ##

  1. **roslaunch wsg\_50\_simulation wsg\_50.launch** to get a complete simulated WSG 50 gripper running in Gazebo.
  1. If you want to teleoperate it, run on a separate terminal: **rosrun wsg\_50\_simulation wsg\_50\_keyboard\_teleop**