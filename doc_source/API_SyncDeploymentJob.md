# SyncDeploymentJob<a name="API_SyncDeploymentJob"></a>

Syncrhonizes robots in a fleet to the latest deployment\. This is helpful if robots were added after a deployment\.

## Request Syntax<a name="API_SyncDeploymentJob_RequestSyntax"></a>

```
POST /syncDeploymentJob HTTP/1.1
Content-type: application/json

{
   "clientRequestToken": "string",
   "fleet": "string"
}
```

## URI Request Parameters<a name="API_SyncDeploymentJob_RequestParameters"></a>

The request does not use any URI parameters\.

## Request Body<a name="API_SyncDeploymentJob_RequestBody"></a>

The request accepts the following data in JSON format\.

 ** [clientRequestToken](#API_SyncDeploymentJob_RequestSyntax) **   <a name="robomaker-SyncDeploymentJob-request-clientRequestToken"></a>
Unique, case\-sensitive identifier that you provide to ensure the idempotency of the request\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 64\.  
Pattern: `[a-zA-Z0-9_\-=]*`   
Required: Yes

 ** [fleet](#API_SyncDeploymentJob_RequestSyntax) **   <a name="robomaker-SyncDeploymentJob-request-fleet"></a>
The target fleet for the synchronization\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 1224\.  
Pattern: `arn:.*`   
Required: Yes

## Response Syntax<a name="API_SyncDeploymentJob_ResponseSyntax"></a>

```
HTTP/1.1 200
Content-type: application/json

{
   "arn": "string",
   "createdAt": number,
   "deploymentApplicationConfigs": [ 
      { 
         "application": "string",
         "applicationVersion": "string",
         "launchConfig": { 
            "environmentVariables": { 
               "string" : "string" 
            },
            "launchFile": "string",
            "packageName": "string",
            "postLaunchFile": "string",
            "preLaunchFile": "string"
         }
      }
   ],
   "deploymentConfig": { 
      "concurrentDeploymentPercentage": number,
      "downloadConditionFile": { 
         "bucket": "string",
         "etag": "string",
         "key": "string"
      },
      "failureThresholdPercentage": number,
      "robotDeploymentTimeoutInSeconds": number
   },
   "failureCode": "string",
   "failureReason": "string",
   "fleet": "string",
   "status": "string"
}
```

## Response Elements<a name="API_SyncDeploymentJob_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 200 response\.

The following data is returned in JSON format by the service\.

 ** [arn](#API_SyncDeploymentJob_ResponseSyntax) **   <a name="robomaker-SyncDeploymentJob-response-arn"></a>
The Amazon Resource Name \(ARN\) of the synchronization request\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 1224\.  
Pattern: `arn:.*` 

 ** [createdAt](#API_SyncDeploymentJob_ResponseSyntax) **   <a name="robomaker-SyncDeploymentJob-response-createdAt"></a>
The time, in milliseconds since the epoch, when the fleet was created\.  
Type: Timestamp

 ** [deploymentApplicationConfigs](#API_SyncDeploymentJob_ResponseSyntax) **   <a name="robomaker-SyncDeploymentJob-response-deploymentApplicationConfigs"></a>
Information about the deployment application configurations\.  
Type: Array of [DeploymentApplicationConfig](API_DeploymentApplicationConfig.md) objects  
Array Members: Fixed number of 1 item\.

 ** [deploymentConfig](#API_SyncDeploymentJob_ResponseSyntax) **   <a name="robomaker-SyncDeploymentJob-response-deploymentConfig"></a>
Information about the deployment configuration\.  
Type: [DeploymentConfig](API_DeploymentConfig.md) object

 ** [failureCode](#API_SyncDeploymentJob_ResponseSyntax) **   <a name="robomaker-SyncDeploymentJob-response-failureCode"></a>
The failure code if the job fails:    
InternalServiceError  
Internal service error\.  
RobotApplicationCrash  
Robot application exited abnormally\.  
SimulationApplicationCrash  
 Simulation application exited abnormally\.  
BadPermissionsRobotApplication  
Robot application bundle could not be downloaded\.  
BadPermissionsSimulationApplication  
Simulation application bundle could not be downloaded\.  
BadPermissionsS3Output  
Unable to publish outputs to customer\-provided S3 bucket\.  
BadPermissionsCloudwatchLogs  
Unable to publish logs to customer\-provided CloudWatch Logs resource\.  
SubnetIpLimitExceeded  
Subnet IP limit exceeded\.  
ENILimitExceeded  
ENI limit exceeded\.  
BadPermissionsUserCredentials  
Unable to use the Role provided\.  
InvalidBundleRobotApplication  
Robot bundle cannot be extracted \(invalid format, bundling error, or other issue\)\.  
InvalidBundleSimulationApplication  
Simulation bundle cannot be extracted \(invalid format, bundling error, or other issue\)\.  
RobotApplicationVersionMismatchedEtag  
Etag for RobotApplication does not match value during version creation\.  
SimulationApplicationVersionMismatchedEtag  
Etag for SimulationApplication does not match value during version creation\.
Type: String  
Valid Values:` ResourceNotFound | EnvironmentSetupError | EtagMismatch | FailureThresholdBreached | RobotDeploymentAborted | RobotDeploymentNoResponse | RobotAgentConnectionTimeout | GreengrassDeploymentFailed | InvalidGreengrassGroup | MissingRobotArchitecture | MissingRobotApplicationArchitecture | MissingRobotDeploymentResource | GreengrassGroupVersionDoesNotExist | LambdaDeleted | ExtractingBundleFailure | PreLaunchFileFailure | PostLaunchFileFailure | BadPermissionError | DownloadConditionFailed | InternalServerError` 

 ** [failureReason](#API_SyncDeploymentJob_ResponseSyntax) **   <a name="robomaker-SyncDeploymentJob-response-failureReason"></a>
The failure reason if the job fails\.  
Type: String  
Length Constraints: Minimum length of 0\. Maximum length of 1024\.  
Pattern: `.*` 

 ** [fleet](#API_SyncDeploymentJob_ResponseSyntax) **   <a name="robomaker-SyncDeploymentJob-response-fleet"></a>
The Amazon Resource Name \(ARN\) of the fleet\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 1224\.  
Pattern: `arn:.*` 

 ** [status](#API_SyncDeploymentJob_ResponseSyntax) **   <a name="robomaker-SyncDeploymentJob-response-status"></a>
The status of the synchronization job\.  
Type: String  
Valid Values:` Pending | Preparing | InProgress | Failed | Succeeded | Canceled` 

## Errors<a name="API_SyncDeploymentJob_Errors"></a>

For information about the errors that are common to all actions, see [Common Errors](CommonErrors.md)\.

 **ConcurrentDeploymentException**   
The failure percentage threshold percentage was met\.  
HTTP Status Code: 400

 **IdempotentParameterMismatchException**   
The request uses the same client token as a previous, but non\-identical request\. Do not reuse a client token with different requests, unless the requests are identical\.   
HTTP Status Code: 400

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

## See Also<a name="API_SyncDeploymentJob_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/robomaker-2018-06-29/SyncDeploymentJob) 
+  [AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/robomaker-2018-06-29/SyncDeploymentJob) 
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/robomaker-2018-06-29/SyncDeploymentJob) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/robomaker-2018-06-29/SyncDeploymentJob) 
+  [AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/robomaker-2018-06-29/SyncDeploymentJob) 
+  [AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/robomaker-2018-06-29/SyncDeploymentJob) 
+  [AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/robomaker-2018-06-29/SyncDeploymentJob) 
+  [AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/robomaker-2018-06-29/SyncDeploymentJob) 
+  [AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/robomaker-2018-06-29/SyncDeploymentJob) 