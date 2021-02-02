# SimulationApplicationConfig<a name="API_SimulationApplicationConfig"></a>

Information about a simulation application configuration\.

## Contents<a name="API_SimulationApplicationConfig_Contents"></a>

 **application**   <a name="robomaker-Type-SimulationApplicationConfig-application"></a>
The application information for the simulation application\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 1224\.  
Pattern: `arn:.*`   
Required: Yes

 **applicationVersion**   <a name="robomaker-Type-SimulationApplicationConfig-applicationVersion"></a>
The version of the simulation application\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 255\.  
Pattern: `(\$LATEST)|[0-9]*`   
Required: No

 **launchConfig**   <a name="robomaker-Type-SimulationApplicationConfig-launchConfig"></a>
The launch configuration for the simulation application\.  
Type: [LaunchConfig](API_LaunchConfig.md) object  
Required: Yes

 **uploadConfigurations**   <a name="robomaker-Type-SimulationApplicationConfig-uploadConfigurations"></a>
Information about upload configurations for the simulation application\.  
Type: Array of [UploadConfiguration](API_UploadConfiguration.md) objects  
Array Members: Minimum number of 0 items\. Maximum number of 10 items\.  
Required: No

 **useDefaultUploadConfigurations**   <a name="robomaker-Type-SimulationApplicationConfig-useDefaultUploadConfigurations"></a>
A Boolean indicating whether to use default upload configurations\. By default, `.ros` and `.gazebo` files are uploaded when the application terminates and all ROS topics will be recorded\.  
If you set this value, you must specify an `outputLocation`\.   
Type: Boolean  
Required: No

 **worldConfigs**   <a name="robomaker-Type-SimulationApplicationConfig-worldConfigs"></a>
A list of world configurations\.  
Type: Array of [WorldConfig](API_WorldConfig.md) objects  
Array Members: Minimum number of 0 items\. Maximum number of 1 item\.  
Required: No

## See Also<a name="API_SimulationApplicationConfig_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/robomaker-2018-06-29/SimulationApplicationConfig) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/robomaker-2018-06-29/SimulationApplicationConfig) 
+  [AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/robomaker-2018-06-29/SimulationApplicationConfig) 
+  [AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/robomaker-2018-06-29/SimulationApplicationConfig) 