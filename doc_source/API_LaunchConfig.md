# LaunchConfig<a name="API_LaunchConfig"></a>

Information about a launch configuration\.

## Contents<a name="API_LaunchConfig_Contents"></a>

 **environmentVariables**   <a name="robomaker-Type-LaunchConfig-environmentVariables"></a>
The environment variables for the application launch\.  
Type: String to string map  
Map Entries: Minimum number of 0 items\. Maximum number of 16 items\.  
Key Length Constraints: Minimum length of 1\. Maximum length of 1024\.  
Key Pattern: `[A-Z_][A-Z0-9_]*`   
Value Length Constraints: Minimum length of 1\. Maximum length of 1024\.  
Value Pattern: `.*`   
Required: No

 **launchFile**   <a name="robomaker-Type-LaunchConfig-launchFile"></a>
The launch file name\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 1024\.  
Pattern: `[a-zA-Z0-9_.\-]*`   
Required: Yes

 **packageName**   <a name="robomaker-Type-LaunchConfig-packageName"></a>
The package name\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 1024\.  
Pattern: `[a-zA-Z0-9_.\-]*`   
Required: Yes

 **portForwardingConfig**   <a name="robomaker-Type-LaunchConfig-portForwardingConfig"></a>
The port forwarding configuration\.  
Type: [PortForwardingConfig](API_PortForwardingConfig.md) object  
Required: No

 **streamUI**   <a name="robomaker-Type-LaunchConfig-streamUI"></a>
Boolean indicating whether a streaming session will be configured for the application\. If `True`, AWS RoboMaker will configure a connection so you can interact with your application as it is running in the simulation\. You must configure and launch the component\. It must have a graphical user interface\.   
Type: Boolean  
Required: No

## See Also<a name="API_LaunchConfig_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/robomaker-2018-06-29/LaunchConfig) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/robomaker-2018-06-29/LaunchConfig) 
+  [AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/robomaker-2018-06-29/LaunchConfig) 
+  [AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/robomaker-2018-06-29/LaunchConfig) 