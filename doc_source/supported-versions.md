# Supported Software and Versions<a name="supported-versions"></a>

AWS RoboMaker supports the following programs, tools, and libraries\.


****  

| Name | Versions Supported | Description | 
| --- | --- | --- | 
| Robot Operating System \(ROS\) |  [Kinetic](http://wiki.ros.org/kinetic) \(end of life April 2021\) [Melodic](http://wiki.ros.org/melodic) \(end of life May 2023\)  | Libraries and tools to help you create robot applications\. | 
| Robot Operating System 2 \(ROS 2\) |  [Dashing](http://docs.ros2.org/dashing) \(in AWS RoboMaker beta\)  | A newer version of ROS still under development\. | 
| Colcon | [Latest](https://github.com/colcon/colcon-core) | Command line tool to bundle ROS robot and simulation applications\. | 
| Gazebo | [7](http://gazebosim.org/blog/gazebo7), [9](http://gazebosim.org/blog/gazebo9) | Tool to simulate robots in an environment\. | 
| rviz | [ROS rviz](http://wiki.ros.org/rviz) [ROS2 rviz2](https://github.com/ros2/rviz)  | Tool to visualize sensor data and state information from ROS in 3D\. | 
| rqt | [latest](http://wiki.ros.org/rqt) | Framework and plugins based on Qt for ROS GUI development\. | 

ROS supports the Python and Ubuntu versions listed below\.


****  

| Name | Version\(s\) Supported | Ubuntu Version\(s\) Supported | 
| --- | --- | --- | 
| ROS Kinetic | Python 2 | Ubuntu Xenial | 
| ROS Melodic | Python 2 | Ubuntu Bionic | 
| ROS2 Dashing | Python 3 | Ubuntu Bionic | 

The following table shows which ROS versions are supported for different AWS RoboMaker features\.


****  

| AWS RoboMaker Feature | ROS version\(s\) Supported | 
| --- | --- | 
| Cloud Extensions |  Melodic, Kinetic, Dashing  | 
| Development Environment \(Create\) |  Melodic, Kinetic, Dashing  | 
| Simulation Job |  Melodic, Kinetic, Dashing  | 
| Fleet Management |  Melodic, Kinetic, Dashing  | 

AWS RoboMaker simulation jobs support the combinations of ROS distribution and Gazebo listed here\.
+ Kinetic and Gazebo 7
+ Kinetic and Gazebo 9
+ Melodic and Gazebo 9
+ Dashing and Gazebo 9

Gazebo supports the following components:


****  

| Component | Version\(s\) Supported | 
| --- | --- | 
| Physics engine |  [ODE](http://opende.sourceforge.net/)  | 
| Rendering engine |  [OGRE](https://www.ogre3d.org/)  | 