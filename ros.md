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

```

## Webviz

Visualizing robotics data in the browser

https://webviz.io/

https://github.com/cruise-automation/webviz

