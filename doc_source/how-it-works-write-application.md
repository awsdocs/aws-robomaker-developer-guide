# Create a Robot Application<a name="how-it-works-write-application"></a>

After your development environment is configured, create a robot application by building on the foundation ROS provides\. ROS relies on a *Computation Graph*, which is a collection of concurrent processes \(nodes\) that perform a task like controlling wheel motors or communicating by passing messages\. 

You do not have to create nodes for common robotic hardware and alogirthms\. For example, there are packages, which are nodes and dependent message definitions, for working with motors, lasers, actuators, lidar, and sensors of all kinds\. There are also packages that consume data from other packages to create maps of the environment, path finding, and more\. For a more comprehensive list, see [ros\.org](http://www.ros.org/browse/list.php)\. 

Using the AWS RoboMaker cloud extensions, capture operational data to aid in troubleshooting and enhance your robot with intelligent functions\. For more information, see [AWS RoboMaker Cloud Extensions](cloud-services-integration.md)\.