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


## Webviz

Visualizing robotics data in the browser

https://webviz.io/

https://github.com/cruise-automation/webviz

