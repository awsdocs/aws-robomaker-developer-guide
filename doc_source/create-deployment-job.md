# Creating a deployment job<a name="create-deployment-job"></a>

Create a deployment job to install a unique version of a robot application on robots in a fleet\. You can define custom environment variables and run a script before and after your application launches on the robot to perform additional configuration\.

You can set fleet and robot deployment timeouts\. The default fleet timeout is 30 days\. The default robot deployment timeout is 5 hours\. For example, if you have 100 robots in your fleet and you deploy to them sequentially with a robot timeout of 7 days, the deployment might take 700 days\. AWS RoboMaker will timeout the deployment at 30 days, the default fleet timeout\. 

For more details about how AWS RoboMaker deploys a robot application, see [How Robot Applications are Deployed](deployment.md#deployment-details)\.

**Note**  
After 90 days, deployment jobs expire and will be deleted\. They will no longer be accessible\.

## Create a deployment job<a name="create-deployment-steps"></a>

------
#### [ Using the console ]<a name="proc-create-deployment-job-con"></a>

**To create a deployment job:**

1. Sign in to the AWS RoboMaker console at [https://console\.aws\.amazon\.com/robomaker/](https://console.aws.amazon.com/robomaker/)\.

1. In the left navigation pane, choose **Fleet Management**, and then choose **Deployments**\.

1. Click **Create deployment**\.

1. In the **Create deployment** page, under **Configuration**, select a **Fleet**\. 

1. Select a **Robot application**\. 

1. Select the **Robot application version** to deploy\. The robot application must have a numbered `applicationVersion` for consistency reasons\. If there are no versions listed, or to create a new version, see [Creating a Robot Application Version](create-robot-application-version.md)\. 

1. Under **Deployment launch config**, specify the **Package name**\. 

1. Specify the **Launch file**\. 

1. Optionally, specify the **Prelaunch file** for your application\. This is a script that is run before the ROS launch file\. It can be used to check the robot environment or other tasks\. A non\-zero exit from the scrip causes the robot deployment to fail\.

   The script should be copied into `$CATKIN_GLOBAL_SHARE_DESTINATION`\.

   For example, add the following configuration to your `CMakeLists.txt`:

   ```
   install(FILES deploymentScripts/post_launch_script.sh
     DESTINATION ${CATKIN_GLOBAL_SHARE_DESTINATION}
   )
   ```

1. Optionally, specify the **Postlaunch file** for your application\. This is a script that is run after launching ROS processes\. It can be used to check the robot environment or other tasks\. A non\-zero exit from the scrip causes the robot deployment to fail\.

   The script should be copied into `$CATKIN_GLOBAL_SHARE_DESTINATION`\.

1. Optionally, under **Environment variables**, type in an environment **Name** and **Value**\. Environment variable names must start with A\-Z or underscore and consist of A\-Z, 0\-9 and underscore\. Names beginning with “AWS” are reserved\.

   Select **Add environment variable** to create additional environment variables\. 

1. Under **Deployment config**, specify a **Concurrent deployment percentage**\. AWS RoboMaker will deploy the robot application concurrently to a percentage of the fleet\. If you have 200 robots in the fleet and choose 10%, deployment will be attempted on 20 robots simultaneously\. 

1. Specify a **Failure threshold percentage**\. Deployment will halt if this percentage of your fleet experiences deployment failure\. 
**Warning**  
Specify a failure threshold percentage larger than concurrent deployment percentage to ensure deployment halts at the threshold\. If the value is smaller, the threshold can be exceeded up to the concurrent deployment percentage\.

1.  Specify a **Robot deployment timeout**\. Deployment to an individual robot will stop if it does not complete before the amount of time specified\.

1. Optionally, provide a **Download condition file in S3**\. The file is a script you can use to verify the robot is ready to download and install the deployment\. For example, you can check to see if the robot is in a charging station and not performing a task \(like flying or moving objects\)\.

1. Optionally, you can **lock S3 file to the latest etag**\. The entity tag is a hash of the Amazon S3 object and reflects changes to the contents of the file, not its metadata\. When selected, AWS RoboMaker will ensure that version is used during deployment\. 

1. Optionally, under **Tags**, specify one or more tags for the deployment\. Tags are words or phrases that act as metadata for identifying and organizing your AWS resources\. Each tag consists of a key and a value\. You can manage tags for your deployment on the **Deployment details** page\.

   Your tags can be populated as environment variables on the robot when the robot application is deployed\. Tags must only contain alphanumeric or underscore characters\. The environment variable name will be formatted as `AWS_ROBOMAKER_ROBOT_TAG_KEY_TAGKEY`, where `TAGKEY` is your tag key\. The tag value will be the environment variable value\. 

   For more about tagging, see [Tagging Your AWS RoboMaker Resources](tagging-robomaker.md)\. 

1. Click **Create** to create the deployment job\. 

------
#### [ Using the AWS CLI ]<a name="proc-create-deployment-job-api"></a>

**Example**  
Here's an example AWS CLI command to create a deployment job\.  

```
$ aws robomaker create-deployment-job --fleet=my-fleet-arn --deployment-application-configs application=my-robotarn,applicationVersion="$LATEST",launchConfig={packageName="cloudwatch_robot",launchFile="cloudwatch_deploy.launch"} --deployment-config concurrentDeploymentPercentage="100",failureThresholdPercentage="100"
```

------