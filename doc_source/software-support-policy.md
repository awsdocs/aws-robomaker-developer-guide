# Software Support Policy<a name="software-support-policy"></a>

AWS RoboMaker supports specific open\-source software versions of ROS, Gazebo and other dependent components\. AWS RoboMaker will deprecate open\-source software versions that are approaching end of life \(EOL\)\. In general, EOL means software will no longer be supported, receive software updates or security updates from its maintainers\. 

AWS RoboMaker will notify you of upcoming deprecation\(s\) of EOL open\-source software\. If your version will be deprecated, you should migrate your AWS RoboMaker resources to a supported ROS distribution so that you continue to benefit from the latest security updates and performance upgrades\. 

If your version will be deprecated, you should migrate your resources to a supported ROS distribution\. For more information about ROS distributions, see [Distributions \(ROS 1\)](http://wiki.ros.org/Distributions) and [Distributions \(ROS 2\)](http://index.ros.org/doc/ros2/Releases)\. 

## Support ending April 2021<a name="software-support-policy-april2021"></a>

Starting April 30, 2021, you will no longer be able to create new ROS Kinetic, Gazebo 7\.1, ROS Dashing or Ubuntu 16\.04 resources in AWS RoboMaker\. However, any existing AWS RoboMaker resources will remain in your account\. If you do not upgrade, functionality of your ROS Kinetic, Gazebo 7\.1, ROS Dashing and Ubuntu 16\.04 resources within AWS RoboMaker features will change or even break\. 

The table below descibes which software suite combinations will be deprecated:




| Software Suite Combination | Deprecated on 4/30/2021? | 
| --- | --- | 
| ROS Kinetic, Gazebo 7\.1, Ubuntu 16\.04 | Yes | 
| ROS Kinetic, Gazebo 9, Ubuntu 16\.04 | Yes | 
| ROS Melodic, Gazebo 9, Ubuntu 16\.04 | No | 
| ROS Dashing, Gazebo 9, Ubuntu 16\.04 | Yes | 

The deprecation will affect the following areas: 
+ **AWS Cloud9 integrated development environments \(IDEs\)**
  + You will have access to all existing ROS Kinetic and ROS Dashing based IDEs\. You can continue to work within the IDE\. The successful execution of the build and bundle process is not guaranteed\. 
  + You will be unable to create new ROS Kinetic and ROS Dashing based IDEs\. 
+ **Robot and simulation applications**
  + You will be unable to create new ROS Kinetic and ROS Dashing based robot applications\.
  + You will be unable to create new simulation applications with ROS Kinetic with Gazebo 7\.1, ROS Kinetic with Gazebo 9, or ROS Dashing with Gazebo 9\. 
  + You will be unable to create a new versions of existing robot or simulation applications using the deprecated ROS and Gazebo versions\. 
+ **Simulation jobs and simulation batches**
  + You will not be able to create new simulation jobs with robot applications and simulation applications using Kinetic, Dashing or Gazebo 7\.1\. 

    Simulation jobs launched prior to the deprecation date and whose duration extends past the deprecation date will continue to run successfully until completed\. With a maximum simulation job duration of 14 days, these jobs can run for a maximum of 14 days post deprecation\. 
+ **Deployment jobs**
  + You will be able to continue and create a deployment job for Kinetic or Dashing based robot applications\. 
+ **Sample applications and cloud extensions**
  + The cloud extensions will no longer be supported in ROS Kinetic and ROS Dashing based applications\. While you can install the cloud extensions into ROS Kinetic and ROS Dashing workspaces, they may or may not work\. 
  + You can no longer select ROS Kinetic or ROS Dashing as the ROS distribution to launch a sample application\. The sample applications may still be downloaded into existing ROS Kinetic and ROS Dashing IDEs, however, they are no longer supported and may break\. 