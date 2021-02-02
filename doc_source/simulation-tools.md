# Simulation Tools<a name="simulation-tools"></a>

AWS RoboMaker provides Gazebo, rqt, rviz and terminal access to interact with running simulation jobs\. 

The simulation tools are configured for each of the applications running in your simulation job\. Each tool is run in the context of one of the applications\. The associated simulation application bundle is sourced to setup the ROS workspace\. For example if you are running a robot application and a simulation application, rqt, rviz and a terminal tool will be sourced with your robot application bundle and Gazebo client and an additional terminal will be sourced with you simulation application bundle\. 

Common tasks include: 
+ [Pause a Running Simulation](simulation-tools-gazebo.md#simulation-tools-gazebo-pause)
+ [View Node Graph](simulation-tools-rqt.md#simulation-tools-rqt-node-graph)
+ [View Robot Sensor Data](simulation-tools-rviz.md#simulation-tools-rviz-view-data)
+ [Inspect ROS Topics and Messages](simulation-tools-terminal.md#simulation-tools-terminal-debug-topics)

The IAM user or role used to create simulation will automatically have permission to access the simulation tools\. If it is a different user or role, it should have the `robomaker:CreateSimulationJob` privilege\. 

You can access simulation tools in the application section of the simulation details page\.

**Topics**
+ [GZClient](simulation-tools-gazebo.md)
+ [rqt](simulation-tools-rqt.md)
+ [rviz](simulation-tools-rviz.md)
+ [Terminal](simulation-tools-terminal.md)