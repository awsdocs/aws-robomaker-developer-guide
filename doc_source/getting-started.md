# Getting Started with AWS RoboMaker<a name="getting-started"></a>

In this section, you learn the basics of how to structure your robot applications and simulation applications, edit code, build, launch new simulations, and deploy applications to robots\. You will use Hello World, an example robot application and simulation application built for TurtleBot3\. The robot rotates in place\. The simulation is an empty world\.
+  **Build a robot application\.** A robot application is a ROS\-based application that runs on a physical robot\. To run your application in a AWS RoboMaker simulation, you need to build an X86\_64 architecture version of the robot application\. 
+  **Build a simulation application\.** A simulation application includes a 3D artificial world and Gazebo plugins that control the movement of a robot within that world\. An X86\_64 architecture version of the simulation application is required\. 
+  **Launch a AWS RoboMaker simulation\.** Simulations can help you develop and test algorithms, train machine learning models, and regression\-test robot applications\.
+  **Deploy a robot application\.** You can build and deploy a robot application to a TurtleBot3 robot\. Deployment is done over\-the\-air using AWS IoT Greengrass\. For more information about TurtleBot3, see [TurtleBot3](https://www.turtlebot.com/)\. 
+  **Access logging and monitoring features\.** You can access service metrics, data written to `stdout`, ROS bags, and Gazebo log files\. Access can be limited using IAM\.

**Topics**
+ [Important Licensing Information](gs-info.md)
+ [Step 1: Create an AWS Account and an Administrator](gs-set-up.md)
+ [Step 2: Run the Hello World Sample Application](gs-build-rundemo.md)
+ [Step 3: Configure Environment and Build Applications](gs-build.md)
+ [Step 4: Run Simulation](gs-simulation.md)
+ [Step 5: Deploy Robot Application](gs-deploy.md)
+ [Step 6: Clean up](gs-cleanup.md)
+ [Additional Sample Robots](gs-tutorials.md)