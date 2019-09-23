# Create a ROS Development Environment<a name="how-it-works-create-environment"></a>

Before you create a robot application, you need a properly configured development environment\. Robot development with AWS RoboMaker depends on a number of open source packages\. 


****  

| Package | Version | Description | 
| --- | --- | --- | 
|  Robot Operating System \(ROS\)  |  [Kinetic](http://wiki.ros.org/kinetic) [Melodic](http://wiki.ros.org/melodic)  |  Libraries and tools to help developers create robot applications\.  | 
|  Colcon  |  [Latest](https://github.com/colcon/colcon-core)  |  A command line tool for bundling ROS robot and simulation applications\.  | 
|  Gazebo  |  [7](http://gazebosim.org/blog/gazebo7)  |  Tool for simulating robots in complex environments\.  | 
|  rviz  |  [latest](http://wiki.ros.org/rviz)  |  ROS Visualizer \(rviz\) is a tool for visualizing sensor data and state information from ROS in 3D\.  | 
|  rqt  |  [latest](http://wiki.ros.org/rqt)  |  Qt\-based framework and plugins for ROS GUI development\.  | 

You can create your own development environment or update an existing development environment to support robot development with AWS RoboMaker\. Most developers use Ubuntu or other supported Linux variants\. Other operating systems might be compatible\. 

AWS RoboMaker provides a quick and easy way to create a development environment that is already configured for robot development\. In a few clicks, you can create a development environment in AWS RoboMaker, install a starter robot application, and begin writing code in your browser\.