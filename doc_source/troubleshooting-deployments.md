# Troubleshooting Deployments<a name="troubleshooting-deployments"></a>

This section provides more information about common issues encountered when deploying a robot application to a fleet\.

## My Deployment Failed<a name="troubleshooting-deployments-failed"></a>

See the following topics for common solutions\.

### Is your robot part of a fleet?<a name="troubleshooting-deployments-notfleet"></a>

A robot must be part of a fleet to receive a deployment\. To check the status of your robots in the AWS RoboMaker console, expand **Fleet management** and then choose **Robots**\. Robots that are registered to a fleet will include the **Fleet name**\. 

### Is AWS IoT Greengrass running on your robot?<a name="troubleshooting-deployments-greengrass-not-started"></a>

To configure and run the AWS IoT Greengrass core software, follow the steps in [Module 1: Environment Setup for Greengrass](https://docs.aws.amazon.com/greengrass/latest/developerguide/module1.html), then follow the steps in [Start AWS Greengrass on the Core Device](https://docs.aws.amazon.com/greengrass/latest/developerguide/gg-device-start.html)\. 

### Is a resource missing?<a name="troubleshooting-deployments-resource-not-found"></a>

In the deployment details page, review the **Failure reason**\. It will list the missing resource\. Verify that the resource exists\. For example, if the robot application is missing, it might have been deleted from the Amazon S3 location or the Amazon S3 etag information might be incorrect\. 

### Did the AWS IoT Greengrass deployment encounter a problem?<a name="troubleshooting-deployments-gg-deployment"></a>

In the deployment details page, review the **Failure reason**\. It will contain more details\.

If AWS IoT Greengrass has problems starting or restarting, look at the AWS IoT Greengrass system logs located on the robot at `/greengrass/ggc/var/log/system/runtime.log`\.

To troubleshoot, see [Troubleshooting AWS IoT Greengrass](https://docs.aws.amazon.com/greengrass/latest/developerguide/gg-troubleshooting.html)\. 

### Do you get error x509: Certificate signed by unknown authority?<a name="troubleshooting-deployments-gg-certificate"></a>

This error might occur if you recently updated your certification or configuration files from AWS RoboMaker or AWS IoT Greengrass in your robot\. The error will appear in the log, `/greengrass/ggc/var/log/system/runtime.log`\. To resolve, upgrade `root.ca.pem` in your robot\. To upgrade, follow step \#5 in [Start AWS IoT Grteengrass on Core Device](https://docs.aws.amazon.com/greengrass/latest/developerguide/gg-device-start.html)\. 

### Was the failure threshold breached?<a name="troubleshooting-deployments-failure-threshold"></a>

Deployment will halt if the failure threshold is breached\. You can raise the threshold to attempt to deploy to more of your fleet\. 

### Is the deployment taking longer than expected?<a name="troubleshooting-deployments-stuck-deploying"></a>

Deployment time depends on the size of the robot application package\. It also depends on the robot network conditions\. If you have many robots and are deploying few concurrently, deployment might take longer\. 

Once started, a single robot deployment timeout is 5 hours\. Use the deployment detail page to identify robots that have an active deployment\. Use `SSH` to connect\. Use the command `ps aux | grep 'greengrass'` to verify AWS IoT Greengrass is running\. To troubleshoot, see [Troubleshooting AWS IoT Greengrass](https://docs.aws.amazon.com/greengrass/latest/developerguide/gg-troubleshooting.html)\. 

### Did your robot receive the deployment request?<a name="troubleshooting-deployments-receive-request"></a>

Your robot might not receive the deployment request if AWS IoT Greengrass is not properly configured and running\. 

First, verify that your robot received the deployment request\. `SSH` to the robot\. Once connected, use `s aux | grep 'greengrass'` to see if AWS IoT Greengrass is running\. check for errors in the log located at `/greengrass/ggc/var/log/user/region/account/aws-robomaker-deployment-function-robot architecture_DO_NOT_DELETE.log`\.

If there are no errors in the log, make sure you have AWS IoT Greengrass version 1\.7\.0 or above installed\. See [Module 1: Environment Setup for Greengrass](https://docs.aws.amazon.com/greengrass/latest/developerguide/module1.html) for more information\.

Next, make sure AWS IoT Greengrass is running with the following command:

```
ps aux | grep 'greengrass'
```

If it is running, look at the AWS IoT Greengrass system logs located on the robot at `/greengrass/ggc/var/log/system/runtime.log`\. See [Troubleshooting AWS IoT Greengrass](https://docs.aws.amazon.com/greengrass/latest/developerguide/gg-troubleshooting.html) for additional troubleshooting information\.

### Will an offline robot get the newest deployment or the last deployment to succeed?<a name="troubleshooting-deployments-robotagentresponsetimeoutexception"></a>

If you received the `RobotAgentResponseTimeoutException` in a new deployment because a robot is unavailable, when it becomes available it will download the latest \(timed out\) deployment\. The robot status will be updated once the robot finished deployment \(will transition from `NoResponse` to `InSync`\. 

### Are you trying to override environment variables sourced in bundle setup scripts?<a name="troubleshooting-deployments-failure-rosvars"></a>

Environment variables sourced from setup bundle scripts can override similar variables defined when a simulation job or deployment job are created\. To avoid this issue, define a new, unique environment variable or change values used in the setup scripts\. 

### ROS did no restart on device reboot<a name="troubleshooting-deployments-failure-no-restart"></a>

This can occur when the Greengrass daemon is not configured to run on restart\. To modify the device `init` system to run the AWS IoT Greengrass daemon, see [Configure the Init System to Start the Greengrass Daemon](https://docs.aws.amazon.com/greengrass/latest/developerguide/gg-core.html#start-on-boot)\. 

### Managing the RoboApplication and default ROS HOME directories<a name="troubleshooting-deployments-failure-clean-up"></a>

AWS IoT Greengrass currently downloads the robot application to the `/home/ggc_user` folder if it was created when you created the “ggc\_user”\. Otherwise it downloads to `/tmp/roboMakerDeploymentPackage`\. And the `/tmp` directory may be cleaned up on reboot\.

If you don’t want the bundle to be removed after the reboot, please ensure the directory `/home/ggc_user` exists and ggc\_user has read and write permissions\. 

The default `ROS_HOME` directory is `/home/ggc_user/ros/home/deployment-id`\. If the ggc\_user home directory does not exist, the default directory is `/tmp/ros/home/deployment-id`\. You can also specify the `ROS_HOME` directory by adding it into the environment variables when you create a deployment job\. The ggc\_user must have read and write permissions to the folder\.

If `/tmp/roboMakerDeploymentPackage` was added to `tmpfiles.d` conf file to persist it to the `tmp` folder, remove it\. 

**Note**  
AWS RoboMaker deployment will clean the robot application folder\. It does not clean the `ROS_HOME` folder\. Use a pre\-deployment or post\-deployment script to manage the directory\. 

## How do I Use Local Libraries on Robot?<a name="troubleshooting-deployments-use-local-libs"></a>

You can override or link the deployed bundle to use local ROS libraries by providing environment variables when you create the deployment job\. For example, set `ROS_ROOT` to the local robot ROS: 

```
"ROS_ROOT":"/opt/ros/kinetic/share/ros"
```