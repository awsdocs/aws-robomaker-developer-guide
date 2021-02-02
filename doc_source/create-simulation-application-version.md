# Creating a Simulation Application Version<a name="create-simulation-application-version"></a>

When you create a simulation application version, you create a snapshot of the `$LATEST` version\. AWS RoboMaker remembers the Amazon S3 path and ETag of the file for the version\. If you change the file at the Amazon S3 path of that version, AWS RoboMaker will not be able to use that version\. AWS RoboMaker does not keep a copy of the version\. 

You can use any version of a robot simulation application when you create a simulation job\. For more information about application versioning, see [Application Versioning](application-versioning.md)\. 

**To create a simulation application version**  
Follow the steps under one of the following tabs\.

------
#### [ Using the console ]<a name="proc-create-simulation-application-version-con"></a>

1. Sign in to the AWS RoboMaker console at [https://console\.aws\.amazon\.com/robomaker/](https://console.aws.amazon.com/robomaker/)\.

1. In the left navigation pane, choose **Development**, and then choose **Simulation applications**\.

1. Select the simulation application **name**\.

1. In the **Simulation applications details** page, select **Create new version**, and then select **Create**\.

------
#### [ Using the AWS CLI ]<a name="proc-create-simulation-application-version-api"></a>

**Example**  
Here's an example AWS CLI command that performs the equivalent of the console\-based create robot application on the other tab\.  

```
$ aws robomaker create-simulation-application-version --name my-simulation-application-arn 
```

------