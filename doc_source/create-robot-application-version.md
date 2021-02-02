# Creating a Robot Application Version<a name="create-robot-application-version"></a>

When you create a robot application version, you create a snapshot of the `$LATEST` version\. AWS RoboMaker remembers the Amazon S3 path and ETag of the file for the version\. If you change the file at the Amazon S3 path of that version, AWS RoboMaker will not be able to use that version\. AWS RoboMaker does not keep a copy of the version\. 

You can use any version of a robot application when you create a simulation job\. For deployments, you must use a numbered version\. For more information about application versioning, see [Application Versioning](application-versioning.md)\. 

**To create a robot application version**  
Follow the steps under one of these tabs\.

------
#### [ Using the console ]<a name="proc-create-robot-application-version-con"></a>

1. Sign in to the AWS RoboMaker console at `[https://console\.aws\.amazon\.com/robomaker/](https://console.aws.amazon.com/robomaker/)`\.

1. In the left navigation pane, choose **Development**, and then choose **Robot applications**\.

1. Choose the robot application **name**\.

1. In the **Robot applications details** page, choose **Create new version**, and then choose **Create**\.

------
#### [ Using the AWS CLI ]<a name="proc-create-robot-application-version-api"></a>

**Example**  
Here's an example AWS CLI command that performs the equivalent of the console\-based steps\.  

```
$ aws robomaker create-robot-application-version --name my-robot-application-arn 
```

------