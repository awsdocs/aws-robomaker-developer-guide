# What Is AWS RoboMaker?<a name="what-is-robomaker"></a>

AWS RoboMaker is a service that makes it easy to create robotics applications at scale\. AWS RoboMaker extends the Robot Operating System \(ROS\) framework with cloud services\. This includes AWS machine learning services\. It includes monitoring services\. It even includes analytics services\. These combine to enable a robot to do several things on it's own\. Stream data, navigate, communicate, comprehend, and learn\. AWS RoboMaker provides a robotics application development environment\. It provides a robotics simulation service, which speeds application testing\. It provides a fleet management service so you can deploy and manage applications remotely\.

## Are You a First\-time User of AWS RoboMaker?<a name="first-time-user"></a>

If you are a first\-time user of AWS RoboMaker, do the following\. 

1. **Read [How It Works](how-it-works.md) ** – An overview of AWS RoboMaker\. Learn the key concepts and components involved in building robot applications and simulations\. Read this topic in the order presented\. 

1. **Read [Getting Started with AWS RoboMaker](getting-started.md)** – How to build your first robot application and simulation\. Explains how to run a simulation job\. Use the sample code provided by AWS RoboMaker\.

1. **Explore robotics topics** – Depending on your needs, do the following\.
   + **Learn about ROS** – In AWS RoboMaker, you build applications and simulations based on the Robot Operating System \(ROS\)\. For more information, see [http://wiki\.ros\.org/ROS/Tutorials](http://wiki.ros.org/ROS/Tutorials)\.
   + **Learn about Gazebo** – A simulator to test robots\. Gazebo helps you test algorithms\. It helps you design robots and train artificial intelligence\. For more information, see [http://gazebosim\.org/tutorials](http://gazebosim.org/tutorials)\. Select version 7 when given the opportunity\.

## Supported Software and Versions<a name="supported-versions"></a>

AWS RoboMaker supports the following:


****  

| Name | Version\(s\) Supported | Description | 
| --- | --- | --- | 
| Robot Operating System \(ROS\) |  [Kinetic](http://wiki.ros.org/kinetic) [Melodic](http://wiki.ros.org/melodic)  | Libraries and tools to help you create robot applications\. | 
| Colcon | [Latest](https://github.com/colcon/colcon-core) | Command line tool to bundle ROS robot and simulation applications\. | 
| Gazebo | [7](http://gazebosim.org/blog/gazebo7), [9](http://gazebosim.org/blog/gazebo9) | Tool to simulate robots in an environment\. | 
| rviz | [latest](http://wiki.ros.org/rviz) | ROS Visualizer \(rviz\) is a tool to visualize sensor data and state information from ROS in 3D\. | 
| rqt | [latest](http://wiki.ros.org/rqt) | Qt\-based framework and plugins for ROS GUI development\. | 

The following table shows which ROS versions are supported for different AWS RoboMaker features:


****  

| AWS RoboMaker Feature | ROS version\(s\) Supported | 
| --- | --- | 
| Cloud Extensions |  Melodic, Kinetic  | 
| Development Environment \(Create\) |  Melodic, Kinetic  | 
| Simulation Job |  Melodic, Kinetic  | 
| Fleet Management |  Melodic, Kinetic  | 

AWS RoboMaker simulation jobs support the following combinations of ROS distribution and Gazebo:
+ Kinetic and Gazebo 7
+ Kinetic and Gazebo 9
+ Melodic and Gazebo 9

Gazebo supports the following components:


****  

| Component | Version\(s\) Supported | 
| --- | --- | 
| Physics Engine |  [ODE](http://opende.sourceforge.net/)  | 
| Rendering Engine |  [OGRE](https://www.ogre3d.org/)  | 