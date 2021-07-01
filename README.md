# TurtleBot3
**1. Install VM with ubuntu 18.04**

**2. Install ROS Melodic**

**3. Open a terminal and use the following commands for installing ROS 1 on remote PC:**
```
$ sudo apt-get update
$ sudo apt-get upgrade
$ wget https://raw.githubusercontent.com/ROBOTIS-GIT/robotis_tools/master/install_ros_melodic.sh
$ chmod 755 ./install_ros_melodic.sh 
$ bash ./install_ros_melodic.sh
```
**4. Install Dependent ROS 1 Packages:**
```
$ sudo apt-get install ros-melodic-joy ros-melodic-teleop-twist-joy \
  ros-melodic-teleop-twist-keyboard ros-melodic-laser-proc \
  ros-melodic-rgbd-launch ros-melodic-depthimage-to-laserscan \
  ros-melodic-rosserial-arduino ros-melodic-rosserial-python \
  ros-melodic-rosserial-server ros-melodic-rosserial-client \
  ros-melodic-rosserial-msgs ros-melodic-amcl ros-melodic-map-server \
  ros-melodic-move-base ros-melodic-urdf ros-melodic-xacro \
  ros-melodic-compressed-image-transport ros-melodic-rqt* \
  ros-melodic-gmapping ros-melodic-navigation ros-melodic-interactive-markers
```
**5. Install TurtleBot3 Packages:**
```
$ sudo apt-get install ros-melodic-dynamixel-sdk
$ sudo apt-get install ros-melodic-turtlebot3-msgs
$ sudo apt-get install ros-melodic-turtlebot3
```
**6. Set TurtleBot3 Model Name:**

_In case of TurtleBot3 Burger_
```
$ echo "export TURTLEBOT3_MODEL=burger" >> ~/.bashrc
```
_In case of TurtleBot3 Waffle Pi_
```
$ echo "export TURTLEBOT3_MODEL=waffle_pi" >> ~/.bashrc
```
**7. Install Simulation Package:**
```
$ cd ~/catkin_ws/src/
$ git clone -b melodic-devel https://github.com/ROBOTIS-GIT/turtlebot3_simulations.git
$ cd ~/catkin_ws && catkin_make
```
**8. Launch Simulation World:**
```
$ roslaunch turtlebot3_gazebo turtlebot3_world.launch
```
**9. Run SLAM Node:**
```
$ roslaunch turtlebot3_slam turtlebot3_slam.launch slam_methods:=gmapping
```
**10. Operate TurtleBot3:**

_In order to teleoperate the TurtleBot3 with the keyboard, launch the teleoperation node with below command in a new terminal window._
```
$ roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch

 Control Your TurtleBot3!
 ---------------------------
 Moving around:
        w
   a    s    d
        x

 w/x : increase/decrease linear velocity
 a/d : increase/decrease angular velocity
 space key, s : force stop

 CTRL-C to quit
```
**11.When the map is created successfully, open a new terminal to save the map:**
```
$ rosrun map_server map_saver -f ~/map
```

