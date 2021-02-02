# Using generated worlds in your simulation<a name="application-worlds-using"></a>

Simulation WorldForge is integrated with AWS RoboMaker\. The worlds you create with Simulation WorldForge are available to simulations in AWS RoboMaker\. You do not need to export, modify, bundle, and upload a world to use it in your simulation\. However, you might need to export and modify a world if your world requires: 
+ Physics that are different from the [default SDF physics](http://sdformat.org/spec?ver=1.6&elem=world)
+ Specialized lighting
+ Custom models

This section provides more information about how you can use generated worlds in your simulation\. You do not need to export a world to use it in your simulation\. 

**Important**  
To learn more about how you are charged for AWS RoboMaker see [AWS RoboMaker Pricing](https://aws.amazon.com/robomaker/pricing/)\. 

**Topics**
+ [Using an imported world in a simulation job](#application-worlds-using-imported)
+ [Using an exported world locally in ROS and Gazebo](#application-worlds-using-locally-rosgazebo)
+ [Using an exported world with custom physics, lights, and models](#application-worlds-using-customize)

## Using an imported world in a simulation job<a name="application-worlds-using-imported"></a>

Simulation WorldForge is integrated into AWS RoboMaker\. You can use a generated world in your simulation by modifying your simulation application launch file\. You do not need to export or modify the world unless you have a unique scenario\. 

**To modify your launch file**

1. Update your simulation application launch file\. 

   ```
   <launch>
     <!-- Always set GUI to false for AWS RoboMaker Simulation
          Use gui:=true on roslaunch command-line to run with gzclient.
     -->
     <arg name="gui" default="false"/>
   
     <include file="$(find aws_robomaker_worldforge_worlds)/launch/launch_world.launch">
       <arg name="gui" value="$(arg gui)"/>
     </include>
       
     <!-- Your other launch commands go here. --> 
   </launch>
   ```

   You can spawn your robot at \(0, 0, 0\)\. The worlds Simulation WorldForge generates are guaranteed to have a 1 meter cylinder clear at \(0, 0, 0\)\.

1. On the console, when you create or clone a simulation job, in the **Import world from WorldForge** section, choose a world\.

   In the AWS CLI, specify the world in `worldConfigs`:

   ```
   worldConfigs={world=arn:aws:robomaker:eu-west-1:MyAccount:world/MyGeneration/MyWorld
   ```

## Using an exported world locally in ROS and Gazebo<a name="application-worlds-using-locally-rosgazebo"></a>

Simulation WorldForge makes it easy to export worlds you can use in your ROS environment\. The world you choose to export is copied to a single \.zip file\. The \.zip file includes all of the assets needed to modify and visualize the worlds using ROS and Gazebo\. It includes the following important folders: 
+ The root folder, **workspace\_src**, is the ROS workspace\. It contains shared models, world data, and other information for the worlds\. It is compatible with ROS 1 and ROS 2\. 
+ **Shared models** is copied to `workspace_src/src/aws_robomaker_worldforge_shared_models/models`\. For example, if the same chair is used in more than one worlds, it will be placed in the shared model folder\. 
+ **World data** is copied to `workspace_src/src/aws_robomaker_worldforge_worlds/worlds/`\. 

**To build and launch the world**

1. Follow the procedure in [Creating a World Export Job](worlds-managing-export-jobs-create.md) to export a world\.

1. `Unzip` the world into an ROS workspace\. 

   ```
   $ cd MyApplication/simulation_ws
   $ unzip MyExportedWorld.zip
   ```

1. Build the world\.

   ```
   $ rosdep install --from-paths src --ignore-src -r -y
   $ colcon build
   ```

1. Launch the world\.

   ```
   $ source install/setup.sh
   $ roslaunch aws_robomaker_worldforge_worlds launch_world.launch gui:=true
   ```

## Using an exported world with custom physics, lights, and models<a name="application-worlds-using-customize"></a>

If your simulation scenario requires customization, you can export and modify the world\. For example, you can apply custom physics, different lighting effects, add custom models, or make other modifications\. 

After the world is exported, you need to modify the `.world` file to include the exported world model\. The `.world` file uses SDF\. For more information about SDF, see [SDFormat](http://sdformat.org/)\. 

**To modify your `.world` file to include the exported world model**

1. Follow the procedure in [Creating a World Export Job](worlds-managing-export-jobs-create.md) to export a world\.

1. Copy the following to your `.world` file\. Make sure the world name matches the exported model name\. 

   ```
   <sdf version="1.6">
     <world name="generation_82856b0yq33y_world_16">  
       <model name="WorldForge World"
         <include>
           <uri>model://generation_82856b0yq33y_world_16</uri>
         </include>
       </model>
       <!-- Your other <world> elements go here -->   
     </world>
   </sdf>
   ```

1. Verify that your launch file includes the modified `.world` file\. Use the updated launch file to launch your simulation\. 