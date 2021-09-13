# ROS

## ROS Workspace: 
* So the workspace represents the working area and any workspace would have a special file that is called `setup`.
* We have setup.bash and setup.sh for a different type of shells.
* This setup file must be executed to enable the worksapce.
* So the workspace is actually the working area that contains the file that we need to run ROS or ROS applications.
* We have to source the setup so that we can use ROS commands. `source setup.sh`
* Recommend to add in .bashrc
* `source /opt/ros/kinetic/setup.bash`
* If not sourced, command like `roscore` or `roscd` and other will give error as not detected./ command not found.
* Default workspace: `roscd` take us to default worksapce `/opt/ros/kinetic`
* Not recommended to work in *default worksapce*.
* Recommend to create our own workspace, where we put our ros projects. So that ROS code and Project code will be different from default one.
* Our worksapce: 
* Create workspace. 
* see: Ros: [create_a_workspace](http://wiki.ros.org/catkin/Tutorials/create_a_workspace)
* see: [ROS workspace](http://wiki.ros.org/catkin/workspaces)
```
$ source /opt/ros/noetic/setup.bash
$ mkdir -p ~/catkin_ws/src
$ cd ~/catkin_ws/
$ catkin_make
```
* Will create two folders `build` and `devel` in same level as `src`. They are Build and development folders.
```
$ ls
build devel src
```
* `roscd` takes us to the default workspace. i.e.  `/opt/ros/kinetic`
* Enable our workspace as default.
* To set our workspace as default, we need to source `setup.bash` from our workspace. i.e. in `./catkin_ws/devel/setup.bash`
* Recommend to add in .bashrc
* add line after default one:
```
source /opt/ros/kinetic/setup.bash
source /home/cube/catkin_ws/devel/setup.bash
echo $ROS_PACKAGE_PATH
```
* echo $ROS_PACKAGE_PATH wil provide ROS PACKAGE PATH, in this case:
* `/home/cube/catkin_ws/src:/opt/ros/kinetic/share`
* Note: our workspace is at beginning, thus `roscd` will take to our workspace.

## ROS Package.
* ROS Project is called as ROS Package.
* Workspace is an working environment
* Package is our own individual project within our workspace environment.
* Package is define inside the worksapce.
* Create package:
* We know we have folders: build, devel, src.
* Our packages are created inside `src` folder.
* Command: **catkin_create_pkg**
```
Syntax:
catkin_create_pkg <package name> < dependencies>
```
* Commmands:
```
$roscd
or
$ cd ./catkin_ws/src/
$ catkin_create_pkg ros_basics std_msgs rospy roscpp
Created file ros_basics/package.xml
Created file ros_basics/CMakeLists.txt
Created folder ros_basics/include/ros_basics
Created folder ros_basics/src
Successfully created files in /home/cube/catkin_ws/src/ros_basics. Please adjust the ...
```
* After creation, need to **compile the workspace**
```
~/catkin_ws/src$ cd ..
~/catkin_ws$
~/catkin_ws$ catkin_make
Base path: /home/cube/catkin_ws
. . .
. . .
-- BUILD_SHARED_LIBS is on
-- -------------------------------------------------------
-- -- traversing 1 packages in topological order:
-- -- - ros_basics
-- -------------------------------------------------------
-- +++ processsing catking package: 'ros_basics'
-- ==> add_subdirectory(ros_basics)
-- Configuration done
-- Generating done
-- Build files have been written to: /home/cube/catkin_ws/build
####
#### Running command: "make -j4 -l4" ln "/home/cube/catking_ws/build"
####
~/catking_ws$
```
* Our project is created.
```
~/catkin_ws$ cd src
~/catkin_ws/src$ ls
CMakeLists.txt   ros_basics
~/catkin_ws/src$ cd ros_basics
~/catkin_ws/src/ros_basics$ ls
include  src  CMakeLists.txt  package.xml
~/catkin_ws/src/ros_basics$
```
* create a project /package space. Folders are empty and we can add our project files.
* When opening from IDE e.g. VSCode, open from folder of catking_ws and not ros_basics.

## ROS Basic project
* Create talker_ros_node. (Publisher)
* Create listener_ros_node. (Subscriber)
* Note: Above are called as nodes

## ROS Working 1.0
* First node in ROS to start is `roscore`
* Than subscriber
* The subscriber will register itself to master and provide informations about itself.
* E.g. subscriber node: turtlesim_node @ http://192.168.0.50:40044
```
Subscriber node info:
/turtlesim,
/turtel1/cmd_vel,
geometry_msg/Twist,
http://192.168.0.50:40044
```
* The publisher is unidirection. It also register with its information.
* E.g. Publisher node turtle_teleop_node @ http://192.168.0.50:40048
```
Publisher node info:
/teleop_turtle,
/turtel1/cmd_vel,
geometry_msg/Twist,
http://192.168.0.50:40048
```
* Both register to Master and master will provide necessary info for them to communicate.
* Note: Publisher and Subscriber will have direct communication.
* Meassage passed from Publisher to Subscriber. Here: /turtle1/cmd_vel (velocity)

## ROS Commands
* `roscore` : run the ros master core
* `rosrun` \<name of package\> \<node\>
* `rosrun ros_basics talker_ros_node`
* `rosrun ros_basics listener_ros_node`
* `rosnode list`: List of nodes in a ROS computation graph, i.e that are running in ROS ecosystem.
* `rostopic list`: List of topics in a ROS compuation graph.
* `rosrun \<ROS Package name\> \<ROS Node name\>`
* `rosnode info \<node name\>
* `rostopic info \<topic name\>
## ROS log
* `roscore`: points to note in log. version, url, name (rosout)
```
PARAMETERS
 * /rosdistro: noetic
 * /rosversion: 1.15.8
ROS_MASTER_URI=http://ubuntu:40020
...
started core service [/rosout]
```
* `rosnode list` and `rostopic list`: When only roscore is running,
```
cube$ rosnode list
/rosout
cube$ rostopic list
/rosout
/rosout_agg
```
* `rosrun turtlesim turtlesim_node. Note name of node: /turtlesim
* rosnode list will show new node
```
cube$ rosrun turtlesim turtlesim_node
[ INFO] [15...]: Starting turtlesim with node name /turtlesim
```

* To list nodes and topics:
```
cube$ rosnode list
/rosout
/turtlesim  <- new node corresponds to turtlesim_node
cube$ 
cube$ 
cube$ rostopic list
/rosout
/rosout_agg
/turtle/cmd_vel          <- 3 new topics from turtlesim_node
/turtle/color_sensor
/turtle/pose
```
* Ros another node, keyboard events. That is a publisher
```
cube$ rosrun turtlesim turtle_teleop_node
Reading from keyboard
\---------------------
Use arrrow keys to move the turtle. 'q' to quit.
```

* in other terminal
```
cube$ rosnode list
/rosout
/teleop_turtle  <- new node.
/turtlesim
cube$
cube$ rostopic list  <- no new topics added as both node use the same.
/rosout
/rosout_agg
/turtle1/cmd_vel
/turtle1/color_sensor
/turtle1/pose
```

* we need publisher, subscriber and a common topic.
* To know the info about node.
```
cube$ rosnode info /turtlesim
\---------
\---------
Node \[/turtlesim\]
Publications:
 * /rosout \[rosgraph_msgs/Log\]
 * /turtle1/color_sensor \[turlesim/Color\]
 * /turtle1/pose \[turtlesim/Pose\]

Subscriptions:
 * /turtle1/cmd_vel \[geometry_msgs/Twist\]

Servcies:
 * /clear
 * /kill
```

* To know about the topic
```
cube$ rostopic info /turtle1/cmd_vel
Type: geometry_msgs/Twist

Publishers:
 * /teleop_turtle (http://ubuntu:33151)

Subscribers:
 * /turtlesim (http://ubuntu:37069)
```

## Webviz

Visualizing robotics data in the browser

https://webviz.io/

https://github.com/cruise-automation/webviz

