# BatchDescribeSimulationJob<a name="API_BatchDescribeSimulationJob"></a>

Describes one or more simulation jobs\.

## Request Syntax<a name="API_BatchDescribeSimulationJob_RequestSyntax"></a>

```
POST /batchDescribeSimulationJob HTTP/1.1
Content-type: application/json

{
   "jobs": [ "string" ]
}
```

## URI Request Parameters<a name="API_BatchDescribeSimulationJob_RequestParameters"></a>

The request does not use any URI parameters\.

## Request Body<a name="API_BatchDescribeSimulationJob_RequestBody"></a>

The request accepts the following data in JSON format\.

 ** [jobs](#API_BatchDescribeSimulationJob_RequestSyntax) **   <a name="robomaker-BatchDescribeSimulationJob-request-jobs"></a>
A list of Amazon Resource Names \(ARNs\) of simulation jobs to describe\.  
Type: Array of strings  
Array Members: Minimum number of 1 item\. Maximum number of 100 items\.  
Length Constraints: Minimum length of 1\. Maximum length of 1224\.  
Pattern: `arn:.*`   
Required: Yes

## Response Syntax<a name="API_BatchDescribeSimulationJob_ResponseSyntax"></a>

```
HTTP/1.1 200
Content-type: application/json

{
   "jobs": [ 
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
         "failureReason": "string",
         "iamRole": "string",
         "lastStartedAt": number,
         "lastUpdatedAt": number,
         "loggingConfig": { 
            "recordAllRosTopics": boolean
         },
         "maxJobDurationInSeconds": number,
         "name": "string",
         "networkInterface": { 
            "networkInterfaceId": "string",
            "privateIpAddress": "string",
            "publicIpAddress": "string"
         },
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
   ],
   "unprocessedJobs": [ "string" ]
}
```

## Response Elements<a name="API_BatchDescribeSimulationJob_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 200 response\.

The following data is returned in JSON format by the service\.

 ** [jobs](#API_BatchDescribeSimulationJob_ResponseSyntax) **   <a name="robomaker-BatchDescribeSimulationJob-response-jobs"></a>
A list of simulation jobs\.  
Type: Array of [SimulationJob](API_SimulationJob.md) objects

 ** [unprocessedJobs](#API_BatchDescribeSimulationJob_ResponseSyntax) **   <a name="robomaker-BatchDescribeSimulationJob-response-unprocessedJobs"></a>
A list of unprocessed simulation job Amazon Resource Names \(ARNs\)\.  
Type: Array of strings  
Array Members: Minimum number of 1 item\. Maximum number of 100 items\.  
Length Constraints: Minimum length of 1\. Maximum length of 1224\.  
Pattern: `arn:.*` 

## Errors<a name="API_BatchDescribeSimulationJob_Errors"></a>

For information about the errors that are common to all actions, see [Common Errors](CommonErrors.md)\.

 **InternalServerException**   
AWS RoboMaker experienced a service issue\. Try your call again\.  
HTTP Status Code: 500

 **InvalidParameterException**   
A parameter specified in a request is not valid, is unsupported, or cannot be used\. The returned message provides an explanation of the error value\.  
HTTP Status Code: 400

 **ResourceNotFoundException**   
The specified resource does not exist\.  
HTTP Status Code: 400

 **ThrottlingException**   
AWS RoboMaker is temporarily unable to process the request\. Try your call again\.  
HTTP Status Code: 400

## See Also<a name="API_BatchDescribeSimulationJob_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/robomaker-2018-06-29/BatchDescribeSimulationJob) 
+  [AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/robomaker-2018-06-29/BatchDescribeSimulationJob) 
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/robomaker-2018-06-29/BatchDescribeSimulationJob) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/robomaker-2018-06-29/BatchDescribeSimulationJob) 
+  [AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/robomaker-2018-06-29/BatchDescribeSimulationJob) 
+  [AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/robomaker-2018-06-29/BatchDescribeSimulationJob) 
+  [AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/robomaker-2018-06-29/BatchDescribeSimulationJob) 
+  [AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/robomaker-2018-06-29/BatchDescribeSimulationJob) 
+  [AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/robomaker-2018-06-29/BatchDescribeSimulationJob) 