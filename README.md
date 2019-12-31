# subo_base

Beginner's tutorial for setting up ROS on RPi, communicating with the base PC and publishing the images from the RPi camera.
The tutorial consists of two parts i.e. RPi workspace and base PC workspace (to be followed in sequence):
1. <https://github.com/nimRobotics/subo_rpi>
2. <https://github.com/nimRobotics/subo_base>

## Setting up the base PC

```sh
aakash@aakash:~$ printenv | grep ROS
aakash@aakash:~$ mkdir -p ~/subo_base/src
aakash@aakash:~$ cd ~/subo_base/
aakash@aakash:~/subo_base$ catkin_make
aakash@aakash:~/subo_base$ source devel/setup.bash
aakash@aakash:~/subo_base$ echo $ROS_PACKAGE_PATH
aakash@aakash:~/subo_base$ cd ~/subo_base/src/
aakash@aakash:~/subo_base/src$ catkin_create_pkg motion_plan std_msgs rospy roscpp
aakash@aakash:~/subo_base/src$ cd ..
aakash@aakash:~/subo_base$ catkin_make
aakash@aakash:~/subo_base$ . ~/subo_base/devel/setup.bash 
aakash@aakash:~/subo_base$ cd src/motion_plan/
aakash@aakash:~/subo_base/src/motion_plan$ mkdir scripts
aakash@aakash:~/subo_base/src/motion_plan$ cd ..
aakash@aakash:~/subo_base/src$ cd ..
aakash@aakash:~/subo_base$ catkin_make
aakash@aakash:~/subo_base$ cd src/motion_plan/scripts
aakash@aakash:~/subo_base/src/motion_plan/scripts$ sudo nano imager.py
aakash@aakash:~/subo_base/src/motion_plan/scripts$ sudo chmod +x imager.py 
aakash@aakash:~/subo_base/src/motion_plan/scripts$ export ROS_MASTER_URI=http://ubiquityrobot.local:11311
aakash@aakash:~/subo_base/src/motion_plan/scripts$ export ROS_IP=10.42.0.81
aakash@aakash:~/subo_base/src/motion_plan/scripts$ rosrun motion_plan imager.py
```