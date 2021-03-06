# CreateSimulationJob<a name="API_CreateSimulationJob"></a>

Creates a simulation job\.

**Note**  
After 90 days, simulation jobs expire and will be deleted\. They will no longer be accessible\. 

## Request Syntax<a name="API_CreateSimulationJob_RequestSyntax"></a>

```
POST /createSimulationJob HTTP/1.1
Content-type: application/json

{
   "clientRequestToken": "string",
   "compute": { 
      "simulationUnitLimit": number
   },
   "dataSources": [ 
      { 
         "name": "string",
         "s3Bucket": "string",
         "s3Keys": [ "string" ]
      }
   ],
   "failureBehavior": "string",
   "iamRole": "string",
   "loggingConfig": { 
      "recordAllRosTopics": boolean
   },
   "maxJobDurationInSeconds": number,
   "outputLocation": { 
      "s3Bucket": "string",
      "s3Prefix": "string"
   },
   "robotApplications": [ 
      { 
         "application": "string",
         "applicationVersion": "string",
         "launchConfig": { 
            "environmentVariables": { 
               "string" : "string" 
            },
            "launchFile": "string",
            "packageName": "string",
            "portForwardingConfig": { 
               "portMappings": [ 
                  { 
                     "applicationPort": number,
                     "enableOnPublicIp": boolean,
                     "jobPort": number
                  }
               ]
            },
            "streamUI": boolean
         },
         "uploadConfigurations": [ 
            { 
               "name": "string",
               "path": "string",
               "uploadBehavior": "string"
            }
         ],
         "useDefaultUploadConfigurations": boolean
      }
   ],
   "simulationApplications": [ 
      { 
         "application": "string",
         "applicationVersion": "string",
         "launchConfig": { 
            "environmentVariables": { 
               "string" : "string" 
            },
            "launchFile": "string",
            "packageName": "string",
            "portForwardingConfig": { 
               "portMappings": [ 
                  { 
                     "applicationPort": number,
                     "enableOnPublicIp": boolean,
                     "jobPort": number
                  }
               ]
            },
            "streamUI": boolean
         },
         "uploadConfigurations": [ 
            { 
               "name": "string",
               "path": "string",
               "uploadBehavior": "string"
            }
         ],
         "useDefaultUploadConfigurations": boolean,
         "worldConfigs": [ 
            { 
               "world": "string"
            }
         ]
      }
   ],
   "tags": { 
      "string" : "string" 
   },
   "vpcConfig": { 
      "assignPublicIp": boolean,
      "securityGroups": [ "string" ],
      "subnets": [ "string" ]
   }
}
```

## URI Request Parameters<a name="API_CreateSimulationJob_RequestParameters"></a>

The request does not use any URI parameters\.

## Request Body<a name="API_CreateSimulationJob_RequestBody"></a>

The request accepts the following data in JSON format\.

 ** [clientRequestToken](#API_CreateSimulationJob_RequestSyntax) **   <a name="robomaker-CreateSimulationJob-request-clientRequestToken"></a>
Unique, case\-sensitive identifier that you provide to ensure the idempotency of the request\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 64\.  
Pattern: `[a-zA-Z0-9_\-=]*`   
Required: No

 ** [compute](#API_CreateSimulationJob_RequestSyntax) **   <a name="robomaker-CreateSimulationJob-request-compute"></a>
Compute information for the simulation job\.  
Type: [Compute](API_Compute.md) object  
Required: No

 ** [dataSources](#API_CreateSimulationJob_RequestSyntax) **   <a name="robomaker-CreateSimulationJob-request-dataSources"></a>
Specify data sources to mount read\-only files from S3 into your simulation\. These files are available under `/opt/robomaker/datasources/data_source_name`\.   
There is a limit of 100 files and a combined size of 25GB for all `DataSourceConfig` objects\. 
Type: Array of [DataSourceConfig](API_DataSourceConfig.md) objects  
Array Members: Minimum number of 1 item\. Maximum number of 5 items\.  
Required: No

 ** [failureBehavior](#API_CreateSimulationJob_RequestSyntax) **   <a name="robomaker-CreateSimulationJob-request-failureBehavior"></a>
The failure behavior the simulation job\.    
Continue  
Restart the simulation job in the same host instance\.  
Fail  
Stop the simulation job and terminate the instance\.
Type: String  
Valid Values:` Fail | Continue`   
Required: No

 ** [iamRole](#API_CreateSimulationJob_RequestSyntax) **   <a name="robomaker-CreateSimulationJob-request-iamRole"></a>
The IAM role name that allows the simulation instance to call the AWS APIs that are specified in its associated policies on your behalf\. This is how credentials are passed in to your simulation job\.   
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 255\.  
Pattern: `arn:aws:iam::\w+:role/.*`   
Required: Yes

 ** [loggingConfig](#API_CreateSimulationJob_RequestSyntax) **   <a name="robomaker-CreateSimulationJob-request-loggingConfig"></a>
The logging configuration\.  
Type: [LoggingConfig](API_LoggingConfig.md) object  
Required: No

 ** [maxJobDurationInSeconds](#API_CreateSimulationJob_RequestSyntax) **   <a name="robomaker-CreateSimulationJob-request-maxJobDurationInSeconds"></a>
The maximum simulation job duration in seconds \(up to 14 days or 1,209,600 seconds\. When `maxJobDurationInSeconds` is reached, the simulation job will status will transition to `Completed`\.  
Type: Long  
Required: Yes

 ** [outputLocation](#API_CreateSimulationJob_RequestSyntax) **   <a name="robomaker-CreateSimulationJob-request-outputLocation"></a>
Location for output files generated by the simulation job\.  
Type: [OutputLocation](API_OutputLocation.md) object  
Required: No

 ** [robotApplications](#API_CreateSimulationJob_RequestSyntax) **   <a name="robomaker-CreateSimulationJob-request-robotApplications"></a>
The robot application to use in the simulation job\.  
Type: Array of [RobotApplicationConfig](API_RobotApplicationConfig.md) objects  
Array Members: Fixed number of 1 item\.  
Required: No

 ** [simulationApplications](#API_CreateSimulationJob_RequestSyntax) **   <a name="robomaker-CreateSimulationJob-request-simulationApplications"></a>
The simulation application to use in the simulation job\.  
Type: Array of [SimulationApplicationConfig](API_SimulationApplicationConfig.md) objects  
Array Members: Fixed number of 1 item\.  
Required: No

 ** [tags](#API_CreateSimulationJob_RequestSyntax) **   <a name="robomaker-CreateSimulationJob-request-tags"></a>
A map that contains tag keys and tag values that are attached to the simulation job\.  
Type: String to string map  
Map Entries: Minimum number of 0 items\. Maximum number of 50 items\.  
Key Length Constraints: Minimum length of 1\. Maximum length of 128\.  
Key Pattern: `[a-zA-Z0-9 _.\-\/+=:]*`   
Value Length Constraints: Minimum length of 0\. Maximum length of 256\.  
Value Pattern: `[a-zA-Z0-9 _.\-\/+=:]*`   
Required: No

 ** [vpcConfig](#API_CreateSimulationJob_RequestSyntax) **   <a name="robomaker-CreateSimulationJob-request-vpcConfig"></a>
If your simulation job accesses resources in a VPC, you provide this parameter identifying the list of security group IDs and subnet IDs\. These must belong to the same VPC\. You must provide at least one security group and one subnet ID\.   
Type: [VPCConfig](API_VPCConfig.md) object  
Required: No

## Response Syntax<a name="API_CreateSimulationJob_ResponseSyntax"></a>

```
HTTP/1.1 200
Content-type: application/json

{
   "arn": "string",
   "clientRequestToken": "string",
   "compute": { 
      "simulationUnitLimit": number
   },
   "dataSources": [ 
      { 
         "name": "string",
         "s3Bucket": "string",
         "s3Keys": [ 
            { 
               "etag": "string",
               "s3Key": "string"
            }
         ]
      }
   ],
   "failureBehavior": "string",
   "failureCode": "string",
   "iamRole": "string",
   "lastStartedAt": number,
   "lastUpdatedAt": number,
   "loggingConfig": { 
      "recordAllRosTopics": boolean
   },
   "maxJobDurationInSeconds": number,
   "outputLocation": { 
      "s3Bucket": "string",
      "s3Prefix": "string"
   },
   "robotApplications": [ 
      { 
         "application": "string",
         "applicationVersion": "string",
         "launchConfig": { 
            "environmentVariables": { 
               "string" : "string" 
            },
            "launchFile": "string",
            "packageName": "string",
            "portForwardingConfig": { 
               "portMappings": [ 
                  { 
                     "applicationPort": number,
                     "enableOnPublicIp": boolean,
                     "jobPort": number
                  }
               ]
            },
            "streamUI": boolean
         },
         "uploadConfigurations": [ 
            { 
               "name": "string",
               "path": "string",
               "uploadBehavior": "string"
            }
         ],
         "useDefaultUploadConfigurations": boolean
      }
   ],
   "simulationApplications": [ 
      { 
         "application": "string",
         "applicationVersion": "string",
         "launchConfig": { 
            "environmentVariables": { 
               "string" : "string" 
            },
            "launchFile": "string",
            "packageName": "string",
            "portForwardingConfig": { 
               "portMappings": [ 
                  { 
                     "applicationPort": number,
                     "enableOnPublicIp": boolean,
                     "jobPort": number
                  }
               ]
            },
            "streamUI": boolean
         },
         "uploadConfigurations": [ 
            { 
               "name": "string",
               "path": "string",
               "uploadBehavior": "string"
            }
         ],
         "useDefaultUploadConfigurations": boolean,
         "worldConfigs": [ 
            { 
               "world": "string"
            }
         ]
      }
   ],
   "simulationTimeMillis": number,
   "status": "string",
   "tags": { 
      "string" : "string" 
   },
   "vpcConfig": { 
      "assignPublicIp": boolean,
      "securityGroups": [ "string" ],
      "subnets": [ "string" ],
      "vpcId": "string"
   }
}
```

## Response Elements<a name="API_CreateSimulationJob_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 200 response\.

The following data is returned in JSON format by the service\.

 ** [arn](#API_CreateSimulationJob_ResponseSyntax) **   <a name="robomaker-CreateSimulationJob-response-arn"></a>
The Amazon Resource Name \(ARN\) of the simulation job\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 1224\.  
Pattern: `arn:.*` 

 ** [clientRequestToken](#API_CreateSimulationJob_ResponseSyntax) **   <a name="robomaker-CreateSimulationJob-response-clientRequestToken"></a>
Unique, case\-sensitive identifier that you provide to ensure the idempotency of the request\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 64\.  
Pattern: `[a-zA-Z0-9_\-=]*` 

 ** [compute](#API_CreateSimulationJob_ResponseSyntax) **   <a name="robomaker-CreateSimulationJob-response-compute"></a>
Compute information for the simulation job\.  
Type: [ComputeResponse](API_ComputeResponse.md) object

 ** [dataSources](#API_CreateSimulationJob_ResponseSyntax) **   <a name="robomaker-CreateSimulationJob-response-dataSources"></a>
The data sources for the simulation job\.  
Type: Array of [DataSource](API_DataSource.md) objects

 ** [failureBehavior](#API_CreateSimulationJob_ResponseSyntax) **   <a name="robomaker-CreateSimulationJob-response-failureBehavior"></a>
the failure behavior for the simulation job\.  
Type: String  
Valid Values:` Fail | Continue` 

 ** [failureCode](#API_CreateSimulationJob_ResponseSyntax) **   <a name="robomaker-CreateSimulationJob-response-failureCode"></a>
The failure code of the simulation job if it failed:    
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
Valid Values:` InternalServiceError | RobotApplicationCrash | SimulationApplicationCrash | BadPermissionsRobotApplication | BadPermissionsSimulationApplication | BadPermissionsS3Object | BadPermissionsS3Output | BadPermissionsCloudwatchLogs | SubnetIpLimitExceeded | ENILimitExceeded | BadPermissionsUserCredentials | InvalidBundleRobotApplication | InvalidBundleSimulationApplication | InvalidS3Resource | LimitExceeded | MismatchedEtag | RobotApplicationVersionMismatchedEtag | SimulationApplicationVersionMismatchedEtag | ResourceNotFound | RequestThrottled | BatchTimedOut | BatchCanceled | InvalidInput | WrongRegionS3Bucket | WrongRegionS3Output | WrongRegionRobotApplication | WrongRegionSimulationApplication | UploadContentMismatchError` 

 ** [iamRole](#API_CreateSimulationJob_ResponseSyntax) **   <a name="robomaker-CreateSimulationJob-response-iamRole"></a>
The IAM role that allows the simulation job to call the AWS APIs that are specified in its associated policies on your behalf\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 255\.  
Pattern: `arn:aws:iam::\w+:role/.*` 

 ** [lastStartedAt](#API_CreateSimulationJob_ResponseSyntax) **   <a name="robomaker-CreateSimulationJob-response-lastStartedAt"></a>
The time, in milliseconds since the epoch, when the simulation job was last started\.  
Type: Timestamp

 ** [lastUpdatedAt](#API_CreateSimulationJob_ResponseSyntax) **   <a name="robomaker-CreateSimulationJob-response-lastUpdatedAt"></a>
The time, in milliseconds since the epoch, when the simulation job was last updated\.  
Type: Timestamp

 ** [loggingConfig](#API_CreateSimulationJob_ResponseSyntax) **   <a name="robomaker-CreateSimulationJob-response-loggingConfig"></a>
The logging configuration\.  
Type: [LoggingConfig](API_LoggingConfig.md) object

 ** [maxJobDurationInSeconds](#API_CreateSimulationJob_ResponseSyntax) **   <a name="robomaker-CreateSimulationJob-response-maxJobDurationInSeconds"></a>
The maximum simulation job duration in seconds\.   
Type: Long

 ** [outputLocation](#API_CreateSimulationJob_ResponseSyntax) **   <a name="robomaker-CreateSimulationJob-response-outputLocation"></a>
Simulation job output files location\.  
Type: [OutputLocation](API_OutputLocation.md) object

 ** [robotApplications](#API_CreateSimulationJob_ResponseSyntax) **   <a name="robomaker-CreateSimulationJob-response-robotApplications"></a>
The robot application used by the simulation job\.  
Type: Array of [RobotApplicationConfig](API_RobotApplicationConfig.md) objects  
Array Members: Fixed number of 1 item\.

 ** [simulationApplications](#API_CreateSimulationJob_ResponseSyntax) **   <a name="robomaker-CreateSimulationJob-response-simulationApplications"></a>
The simulation application used by the simulation job\.  
Type: Array of [SimulationApplicationConfig](API_SimulationApplicationConfig.md) objects  
Array Members: Fixed number of 1 item\.

 ** [simulationTimeMillis](#API_CreateSimulationJob_ResponseSyntax) **   <a name="robomaker-CreateSimulationJob-response-simulationTimeMillis"></a>
The simulation job execution duration in milliseconds\.  
Type: Long

 ** [status](#API_CreateSimulationJob_ResponseSyntax) **   <a name="robomaker-CreateSimulationJob-response-status"></a>
The status of the simulation job\.  
Type: String  
Valid Values:` Pending | Preparing | Running | Restarting | Completed | Failed | RunningFailed | Terminating | Terminated | Canceled` 

 ** [tags](#API_CreateSimulationJob_ResponseSyntax) **   <a name="robomaker-CreateSimulationJob-response-tags"></a>
The list of all tags added to the simulation job\.  
Type: String to string map  
Map Entries: Minimum number of 0 items\. Maximum number of 50 items\.  
Key Length Constraints: Minimum length of 1\. Maximum length of 128\.  
Key Pattern: `[a-zA-Z0-9 _.\-\/+=:]*`   
Value Length Constraints: Minimum length of 0\. Maximum length of 256\.  
Value Pattern: `[a-zA-Z0-9 _.\-\/+=:]*` 

 ** [vpcConfig](#API_CreateSimulationJob_ResponseSyntax) **   <a name="robomaker-CreateSimulationJob-response-vpcConfig"></a>
Information about the vpc configuration\.  
Type: [VPCConfigResponse](API_VPCConfigResponse.md) object

## Errors<a name="API_CreateSimulationJob_Errors"></a>

For information about the errors that are common to all actions, see [Common Errors](CommonErrors.md)\.

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

 **ServiceUnavailableException**   
The request has failed due to a temporary failure of the server\.  
HTTP Status Code: 503

 **ThrottlingException**   
AWS RoboMaker is temporarily unable to process the request\. Try your call again\.  
HTTP Status Code: 400

## See Also<a name="API_CreateSimulationJob_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/robomaker-2018-06-29/CreateSimulationJob) 
+  [AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/robomaker-2018-06-29/CreateSimulationJob) 
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/robomaker-2018-06-29/CreateSimulationJob) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/robomaker-2018-06-29/CreateSimulationJob) 
+  [AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/robomaker-2018-06-29/CreateSimulationJob) 
+  [AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/robomaker-2018-06-29/CreateSimulationJob) 
+  [AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/robomaker-2018-06-29/CreateSimulationJob) 
+  [AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/robomaker-2018-06-29/CreateSimulationJob) 
+  [AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/robomaker-2018-06-29/CreateSimulationJob) 