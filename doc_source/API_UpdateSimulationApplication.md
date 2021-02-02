# UpdateSimulationApplication<a name="API_UpdateSimulationApplication"></a>

Updates a simulation application\.

## Request Syntax<a name="API_UpdateSimulationApplication_RequestSyntax"></a>

```
POST /updateSimulationApplication HTTP/1.1
Content-type: application/json

{
   "application": "string",
   "currentRevisionId": "string",
   "renderingEngine": { 
      "name": "string",
      "version": "string"
   },
   "robotSoftwareSuite": { 
      "name": "string",
      "version": "string"
   },
   "simulationSoftwareSuite": { 
      "name": "string",
      "version": "string"
   },
   "sources": [ 
      { 
         "architecture": "string",
         "s3Bucket": "string",
         "s3Key": "string"
      }
   ]
}
```

## URI Request Parameters<a name="API_UpdateSimulationApplication_RequestParameters"></a>

The request does not use any URI parameters\.

## Request Body<a name="API_UpdateSimulationApplication_RequestBody"></a>

The request accepts the following data in JSON format\.

 ** [application](#API_UpdateSimulationApplication_RequestSyntax) **   <a name="robomaker-UpdateSimulationApplication-request-application"></a>
The application information for the simulation application\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 1224\.  
Pattern: `arn:.*`   
Required: Yes

 ** [currentRevisionId](#API_UpdateSimulationApplication_RequestSyntax) **   <a name="robomaker-UpdateSimulationApplication-request-currentRevisionId"></a>
The revision id for the robot application\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 40\.  
Pattern: `[a-zA-Z0-9_.\-]*`   
Required: No

 ** [renderingEngine](#API_UpdateSimulationApplication_RequestSyntax) **   <a name="robomaker-UpdateSimulationApplication-request-renderingEngine"></a>
The rendering engine for the simulation application\.  
Type: [RenderingEngine](API_RenderingEngine.md) object  
Required: No

 ** [robotSoftwareSuite](#API_UpdateSimulationApplication_RequestSyntax) **   <a name="robomaker-UpdateSimulationApplication-request-robotSoftwareSuite"></a>
Information about the robot software suite \(ROS distribution\)\.  
Type: [RobotSoftwareSuite](API_RobotSoftwareSuite.md) object  
Required: Yes

 ** [simulationSoftwareSuite](#API_UpdateSimulationApplication_RequestSyntax) **   <a name="robomaker-UpdateSimulationApplication-request-simulationSoftwareSuite"></a>
The simulation software suite used by the simulation application\.  
Type: [SimulationSoftwareSuite](API_SimulationSoftwareSuite.md) object  
Required: Yes

 ** [sources](#API_UpdateSimulationApplication_RequestSyntax) **   <a name="robomaker-UpdateSimulationApplication-request-sources"></a>
The sources of the simulation application\.  
Type: Array of [SourceConfig](API_SourceConfig.md) objects  
Required: Yes

## Response Syntax<a name="API_UpdateSimulationApplication_ResponseSyntax"></a>

```
HTTP/1.1 200
Content-type: application/json

{
   "arn": "string",
   "lastUpdatedAt": number,
   "name": "string",
   "renderingEngine": { 
      "name": "string",
      "version": "string"
   },
   "revisionId": "string",
   "robotSoftwareSuite": { 
      "name": "string",
      "version": "string"
   },
   "simulationSoftwareSuite": { 
      "name": "string",
      "version": "string"
   },
   "sources": [ 
      { 
         "architecture": "string",
         "etag": "string",
         "s3Bucket": "string",
         "s3Key": "string"
      }
   ],
   "version": "string"
}
```

## Response Elements<a name="API_UpdateSimulationApplication_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 200 response\.

The following data is returned in JSON format by the service\.

 ** [arn](#API_UpdateSimulationApplication_ResponseSyntax) **   <a name="robomaker-UpdateSimulationApplication-response-arn"></a>
The Amazon Resource Name \(ARN\) of the updated simulation application\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 1224\.  
Pattern: `arn:.*` 

 ** [lastUpdatedAt](#API_UpdateSimulationApplication_ResponseSyntax) **   <a name="robomaker-UpdateSimulationApplication-response-lastUpdatedAt"></a>
The time, in milliseconds since the epoch, when the simulation application was last updated\.  
Type: Timestamp

 ** [name](#API_UpdateSimulationApplication_ResponseSyntax) **   <a name="robomaker-UpdateSimulationApplication-response-name"></a>
The name of the simulation application\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 255\.  
Pattern: `[a-zA-Z0-9_\-]*` 

 ** [renderingEngine](#API_UpdateSimulationApplication_ResponseSyntax) **   <a name="robomaker-UpdateSimulationApplication-response-renderingEngine"></a>
The rendering engine for the simulation application\.  
Type: [RenderingEngine](API_RenderingEngine.md) object

 ** [revisionId](#API_UpdateSimulationApplication_ResponseSyntax) **   <a name="robomaker-UpdateSimulationApplication-response-revisionId"></a>
The revision id of the simulation application\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 40\.  
Pattern: `[a-zA-Z0-9_.\-]*` 

 ** [robotSoftwareSuite](#API_UpdateSimulationApplication_ResponseSyntax) **   <a name="robomaker-UpdateSimulationApplication-response-robotSoftwareSuite"></a>
Information about the robot software suite \(ROS distribution\)\.  
Type: [RobotSoftwareSuite](API_RobotSoftwareSuite.md) object

 ** [simulationSoftwareSuite](#API_UpdateSimulationApplication_ResponseSyntax) **   <a name="robomaker-UpdateSimulationApplication-response-simulationSoftwareSuite"></a>
The simulation software suite used by the simulation application\.  
Type: [SimulationSoftwareSuite](API_SimulationSoftwareSuite.md) object

 ** [sources](#API_UpdateSimulationApplication_ResponseSyntax) **   <a name="robomaker-UpdateSimulationApplication-response-sources"></a>
The sources of the simulation application\.  
Type: Array of [Source](API_Source.md) objects

 ** [version](#API_UpdateSimulationApplication_ResponseSyntax) **   <a name="robomaker-UpdateSimulationApplication-response-version"></a>
The version of the robot application\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 255\.  
Pattern: `(\$LATEST)|[0-9]*` 

## Errors<a name="API_UpdateSimulationApplication_Errors"></a>

For information about the errors that are common to all actions, see [Common Errors](CommonErrors.md)\.

 **InternalServerException**   
AWS RoboMaker experienced a service issue\. Try your call again\.  
HTTP Status Code: 500

 **InvalidParameterException**   
A parameter specified in a request is not valid, is unsupported, or cannot be used\. The returned message provides an explanation of the error value\.  
HTTP Status Code: 400

 **LimitExceededException**   
The requested resource exceeds the maximum number allowed, or the number of concurrent stream requests exceeds the maximum number allowed\.   
HTTP Status Code: 400

 **ResourceNotFoundException**   
The specified resource does not exist\.  
HTTP Status Code: 400

 **ThrottlingException**   
AWS RoboMaker is temporarily unable to process the request\. Try your call again\.  
HTTP Status Code: 400

## See Also<a name="API_UpdateSimulationApplication_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/robomaker-2018-06-29/UpdateSimulationApplication) 
+  [AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/robomaker-2018-06-29/UpdateSimulationApplication) 
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/robomaker-2018-06-29/UpdateSimulationApplication) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/robomaker-2018-06-29/UpdateSimulationApplication) 
+  [AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/robomaker-2018-06-29/UpdateSimulationApplication) 
+  [AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/robomaker-2018-06-29/UpdateSimulationApplication) 
+  [AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/robomaker-2018-06-29/UpdateSimulationApplication) 
+  [AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/robomaker-2018-06-29/UpdateSimulationApplication) 
+  [AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/robomaker-2018-06-29/UpdateSimulationApplication) 