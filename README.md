# ur5_2f_85_gripper
#build MoveIt! from source and if you want to build own OMPL planner
https://www.notion.so/MoveIt-customize-planner-2edeb5fe86b84e5fa6fd0120eb3876a5

#use robotiq gazebo plugin with mimic joint
https://github.com/roboticsgroup/roboticsgroup_upatras_gazebo_plugins.git

## Add Universal Robots Driver

**Note:** The driver consists of a [C++
library](https://github.com/UniversalRobots/Universal_Robots_Client_Library) that abstracts the
robot's interfaces and a ROS driver on top of that. As the library can be built without ROS support,
it is not a catkin package and therefore requires a different treatment when being built inside the
workspace. See The alternative build method below if you'd like to build the library from source.

If you don't want to build the library from source, it is available as a binary package through the
ROS distribution of ROS melodic and noetic. It will be installed automatically if you
follow the steps below. If you'd like to also build the library from source, please follow the steps
explained in the [next section](#alternative-all-source-build).

```bash
# source global ros
$ source /opt/ros/<your_ros_version>/setup.bash

# create a catkin workspace
$ mkdir -p catkin_ws/src && cd catkin_ws

# clone the driver
$ git clone https://github.com/UniversalRobots/Universal_Robots_ROS_Driver.git src/Universal_Robots_ROS_Driver

# install dependencies
$ sudo apt update -qq
$ rosdep update
$ rosdep install --from-paths src --ignore-src -y

# build the workspace
$ sudo catkin build

# activate the workspace (ie: source it)
$ source devel/setup.bash
```
