# Task-3
## Robot Arm
### 1- Setup your sources.list
###### Setup your computer to accept software from packages.ros.org.
```
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
```
### 2- Set up your keys
```
sudo apt-key adv --keyserver 'hkp://keyserver.ubuntu.com:80' --recv-key C1CF6E31E6BADE8868B172B4F42ED6FBAB17C654
```
### 3- Installation
###### First, make sure your Debian package index is up-to-date:
```
sudo apt-get update
```
### 4- Desktop-Full Install
###### ROS, rqt, rviz, robot-generic libraries, 2D/3D simulators, navigation and 2D/3D perception
```
sudo apt-get install ros-kinetic-desktop-full
```
### 5- Find available packages
```
apt-cache search ros-kinetic
```
### 6- Environment setup
###### It's convenient if the ROS environment variables are automatically added to your bash session every time a new shell is launched
```
echo "source /opt/ros/kinetic/setup.bash" >> ~/.bashrc
source ~/.bashrc
```
### 7- Dependencies for building packages
###### To install this tool and other dependencies for building ROS packages
```
sudo apt install python-rosdep python-rosinstall python-rosinstall-generator python-wstool build-essential
```
### 8- Initialize rosdep
###### Before you can use many ROS tools, you will need to initialize rosdep. rosdep enables you to easily install system dependencies for source you want to compile and is required to run some core components in ROS
```
sudo apt install python-rosdep
sudo rosdep init
rosdep update
```
### 9- Install Prebuilt Package
```
sudo apt-get install ros-noetic-catkin
```
### 10- Building a catkin workspace and sourcing the setup file
###### Now you need to build the packages in the catkin workspace
```
mkdir -p ~/catkin_ws/src
cd ~/catkin_ws/
catkin_make
cd ~/catkin_ws/src
```
### 11- Use source-installed rosdep
###### Clone the development repository
```
git clone https://github.com/smart-methods/arduino_robot_arm.git 
cd ~/catkin_ws
```
### 12- Install dependency of all packages in the workspace
###### This usecase shows even more powerful feature of rosdep
```
rosdep install --from-paths src --ignore-src -r -y
```


