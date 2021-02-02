# Application Versioning<a name="application-versioning"></a>

AWS RoboMaker supports creating more than one version of your robot applications and simulation applications\. This helps you control which code your robots and simulations use\. A version is a numbered snapshot of the `$LATEST` version of your application\. You can create a version to use in different parts of your development workflow\. For example, development, beta deployment, or production\. 

When you version an AWS RoboMaker robot application or simulation application you create a snapshot of the application\. AWS RoboMaker remembers the Amazon S3 path and ETag of the file for each version\. You can use the version of the application as it existed when the version was made provided it still exists in the Amazon S3 path and has not been altered \(its ETag is unchanged\)\. 

You can create a maximum of 40 versions per application\.

**Topics**
+ [The $LATEST Version](#latest-version)
+ [Updating an Application Version](#updating-version)
+ [Deleting an Application Version](#delete-version)

## The $LATEST Version<a name="latest-version"></a>

When you create a version, AWS RoboMaker takes a snapshot of the `$LATEST` version and increments the version number by 1\. AWS RoboMaker remembers the Amazon S3 path and ETag of the file\. The path is used to retrieve the file\. The ETag is used to confirm it has not changed\. Version numbers are never reused\. For example, if your latest version is 10 and you remove it and then create a new version, the new version will be version 11\. 

You can update the `$LATST` version as you develop your application\. When you select the `$LATEST` version, it will be retrieved from the Amazon S3 location you specify\. For example, if you start a simulation job using the latest version of your robot application and simulation application, then make changes to the robot application at the Amazon S3 path, and then restart the simulation job, the updated robot application will be used\. 

 When you deploy a robot application, you must select a specific numbered version to deploy\. For more information on how to create a robot application version, see [Creating a Robot Application Version](create-robot-application-version.md)\. 

For more information how to create a simulation application version, see [Creating a Simulation Application Version](create-simulation-application-version.md)\. For more information about ETags, see [ Common Response Headers](https://docs.aws.amazon.com/AmazonS3/latest/API/RESTCommonResponseHeaders.html)\.

## Updating an Application Version<a name="updating-version"></a>

You can update only the `$LATEST` version of an AWS RoboMaker application \. When you do this, it is available to use in AWS RoboMaker\. For example, if you restart a simulation job, the latest version of the applications will be used in the simulation\. 

For more information, see [Updating a Robot Application](update-robot-application.md) and [Updating a Simulation Application](update-simulation-application.md)\.

## Deleting an Application Version<a name="delete-version"></a>

When you no longer need an application version, delete it\. For more information, see [Deleting a Robot Application Version](delete-robot-application-version.md) and [Deleting a Simulation Application Version](delete-simulation-application-version.md)\. 