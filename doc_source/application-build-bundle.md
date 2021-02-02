# Building and Bundling Robotic Applications with Colcon<a name="application-build-bundle"></a>

AWS RoboMaker works with robotics applications built and bundled with colcon\. `colcon` is a command line tool built by the [Open Source Robotics Foundation](https://www.openrobotics.org/) \(OSRF\)\. It automates the building and bundling of ROS and ROS2 applications\. It should be a drop\-in replacement for `catkin_make`\. 

 For more information about `colcon`, see [Colcon](https://colcon.readthedocs.io/)\. If you experience issues while building with `colcon`, see [colcon\-ros](https://github.com/colcon/colcon-ros)\. For problems bundling with `colcon`, see [colcon\-bundle](https://github.com/colcon/colcon-bundle)\. 

**Topics**
+ [Installing Colcon](#install-colcon)
+ [Using Colcon to Build and Bundle](#use-colcon)

## Installing Colcon<a name="install-colcon"></a>

Use the following commands to install `colcon` and `colcon-bundle`:

```
apt-get update
apt-get install python3-pip python3-apt
pip3 install -U setuptools
pip3 install -U colcon-common-extensions colcon-ros-bundle
```

If you already have `colcon` installed, you can install bundling support with the following command:

```
pip3 install -U colcon-ros-bundle
```

## Using Colcon to Build and Bundle<a name="use-colcon"></a>

If you are migrating from `catkin`, verify the following before you use colcon to build and bundle your robotic application:
+ All of the folders you want to include in the application are defined\. For example, the following code includes common ROS folders `launch` and `nodes` in the install directory created by `colcon`\. You can replace replace `launch` and `nodes` with the folders used by your application\. Make sure this block is defined in your `cMakeLists.txt` file: 

  ```
  install(DIRECTORY launch nodes
    DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
  )
  ```

   For more information on `CMakeList.txt` and `catkin`, see [catkin / CMakeLists\.txt](http://wiki.ros.org/catkin/CMakeLists.txt) on [ROS\.org](ros.org)\. 
+ All of your application dependencies are installed through `rosdep` or `pip`\. Make sure all of your dependencies are added to `package.xml` and/or an included `requirements.txt` file\. If a dependency is not available in the public rosdep sources lists, you can create a custom sources list\. To do this, follow the instructions on [ROS\.org](http://wiki.ros.org/rosdep/rosdep.yaml)\. For more information about troubleshooting, see [Troubleshooting Colcon Build and Bundle](troubleshooting-colcon.md)\. 
+ All of the arguments you are pathing through your launch file are defined as environment variables in the AWS RoboMaker simulation job\. You can define environment variables using the console or the AWS RoboMaker SDK\. For an example using an environment variable, see [Using Environment Variables to Configure Play Back](simulation-job-playback-rosbags.md#simulation-job-playback-rosbags-example-envvars)\.

Use the following commands to build and then bundle your robotics application:

```
cd robotic-application-workspace
colcon build
colcon bundle
```

You can test your application prior to bundling and uploading with the following:

```
source install/setup.sh
roslaunch package_name launch_file
```