# RobotApplicationConfig<a name="API_RobotApplicationConfig"></a>

Application configuration information for a robot\.

## Contents<a name="API_RobotApplicationConfig_Contents"></a>

 **application**   <a name="robomaker-Type-RobotApplicationConfig-application"></a>
The application information for the robot application\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 1224\.  
Pattern: `arn:.*`   
Required: Yes

 **applicationVersion**   <a name="robomaker-Type-RobotApplicationConfig-applicationVersion"></a>
The version of the robot application\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 255\.  
Pattern: `(\$LATEST)|[0-9]*`   
Required: No

 **launchConfig**   <a name="robomaker-Type-RobotApplicationConfig-launchConfig"></a>
The launch configuration for the robot application\.  
Type: [LaunchConfig](API_LaunchConfig.md) object  
Required: Yes

 **uploadConfigurations**   <a name="robomaker-Type-RobotApplicationConfig-uploadConfigurations"></a>
The upload configurations for the robot application\.  
Type: Array of [UploadConfiguration](API_UploadConfiguration.md) objects  
Array Members: Minimum number of 0 items\. Maximum number of 10 items\.  
Required: No

 **useDefaultUploadConfigurations**   <a name="robomaker-Type-RobotApplicationConfig-useDefaultUploadConfigurations"></a>
A Boolean indicating whether to use default upload configurations\. By default, `.ros` and `.gazebo` files are uploaded when the application terminates and all ROS topics will be recorded\.  
If you set this value, you must specify an `outputLocation`\.   
Type: Boolean  
Required: No

## See Also<a name="API_RobotApplicationConfig_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/robomaker-2018-06-29/RobotApplicationConfig) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/robomaker-2018-06-29/RobotApplicationConfig) 
+  [AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/robomaker-2018-06-29/RobotApplicationConfig) 
+  [AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/robomaker-2018-06-29/RobotApplicationConfig) 