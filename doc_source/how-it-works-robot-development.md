# Robotics Development with AWS RoboMaker<a name="how-it-works-robot-development"></a>

This section describes a typical robot development workflow and tells how you accomplish those tasks with AWS RoboMaker\.

Robot application development usually begins after you choose your physical robot hardware\. First, you create a development environment and load the tools to build an application\. Next, create the robot application\. Write custom logic that responds to environmental data\. Next, build simulations, or models of the world that your robot will inhabit\. Collect data about how your robot performs in simulation jobs\. When your tests are complete, deploy your robot application to your physical robots\. Monitor them and update the software when needed\. 

As a robot developer, you typically perform the following activities\.

1. **Create a ROS development environment** — To create a robot application, you need an environment configured for ROS development along with tools like Colcon to build and bundle the application\. You'll also need tools to help you cross\-compile the application for your physical robot\. Using an integrated development environment makes it easier\. 

   In AWS RoboMaker, you can create an AWS Cloud9 development environment that is already configured with the tools to develop robot applications\. You can also use your existing environment\.

1. **Create the robot application** — This is where you get to write code\. Build on the foundation provided by ROS and integrate functionality provided by the community\. The application you create works with your robot hardware, provides intelligence, and works with the cloud\. 

1. **Develop simulation and testing data** — In this stage, run your robot application in simulated environments\. Collect sensor data and other performance information produced by the simulation\. It can take many iterations with different simulation applications to complete the robot implementation\. 

1. **Deploy to robot fleets** — When your robot application performs as expected, you are ready to deploy it to your robot\. In AWS RoboMaker, a robot must belong to a fleet \(a group of robots\) in order to receive a robot application deployment\. Each virtual robot in AWS RoboMaker represents a physical robot\. 

1. **Monitor and update robots** — Your robots are interacting in the world\! Refine your robot application using data you collect using AWS RoboMaker cloud extensions\. 

The following sections explore the details of each step\.