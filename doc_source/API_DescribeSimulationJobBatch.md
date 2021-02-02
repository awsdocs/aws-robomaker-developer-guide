# DescribeSimulationJobBatch<a name="API_DescribeSimulationJobBatch"></a>

Describes a simulation job batch\.

## Request Syntax<a name="API_DescribeSimulationJobBatch_RequestSyntax"></a>

```
POST /describeSimulationJobBatch HTTP/1.1
Content-type: application/json

{
   "batch": "string"
}
```

## URI Request Parameters<a name="API_DescribeSimulationJobBatch_RequestParameters"></a>

The request does not use any URI parameters\.

## Request Body<a name="API_DescribeSimulationJobBatch_RequestBody"></a>

The request accepts the following data in JSON format\.

 ** [batch](#API_DescribeSimulationJobBatch_RequestSyntax) **   <a name="robomaker-DescribeSimulationJobBatch-request-batch"></a>
The id of the batch to describe\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 1224\.  
Pattern: `arn:.*`   
Required: Yes

## Response Syntax<a name="API_DescribeSimulationJobBatch_ResponseSyntax"></a>

```
HTTP/1.1 200
Content-type: application/json

{
   "arn": "string",
   "batchPolicy": { 
      "maxConcurrency": number,
      "timeoutInSeconds": number
   },
   "clientRequestToken": "string",
   "createdAt": number,
   "createdRequests": [ 
      { 
         "arn": "string",
         "dataSourceNames": [ "string" ],
         "lastUpdatedAt": number,
         "name": "string",
         "robotApplicationNames": [ "string" ],
         "simulationApplicationNames": [ "string" ],
         "status": "string"
      }
   ],
   "failedRequests": [ 
      { 
         "failedAt": number,
         "failureCode": "string",
         "failureReason": "string",
         "request": { 
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
            "useDefaultApplications": boolean,
            "vpcConfig": { 
               "assignPublicIp": boolean,
               "securityGroups": [ "string" ],
               "subnets": [ "string" ]
            }
         }
      }
   ],
   "failureCode": "string",
   "failureReason": "string",
   "lastUpdatedAt": number,
   "pendingRequests": [ 
      { 
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
         "useDefaultApplications": boolean,
         "vpcConfig": { 
            "assignPublicIp": boolean,
            "securityGroups": [ "string" ],
            "subnets": [ "string" ]
         }
      }
   ],
   "status": "string",
   "tags": { 
      "string" : "string" 
   }
}
```

## Response Elements<a name="API_DescribeSimulationJobBatch_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 200 response\.

The following data is returned in JSON format by the service\.

 ** [arn](#API_DescribeSimulationJobBatch_ResponseSyntax) **   <a name="robomaker-DescribeSimulationJobBatch-response-arn"></a>
The Amazon Resource Name \(ARN\) of the batch\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 1224\.  
Pattern: `arn:.*` 

 ** [batchPolicy](#API_DescribeSimulationJobBatch_ResponseSyntax) **   <a name="robomaker-DescribeSimulationJobBatch-response-batchPolicy"></a>
The batch policy\.  
Type: [BatchPolicy](API_BatchPolicy.md) object

 ** [clientRequestToken](#API_DescribeSimulationJobBatch_ResponseSyntax) **   <a name="robomaker-DescribeSimulationJobBatch-response-clientRequestToken"></a>
Unique, case\-sensitive identifier that you provide to ensure the idempotency of the request\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 64\.  
Pattern: `[a-zA-Z0-9_\-=]*` 

 ** [createdAt](#API_DescribeSimulationJobBatch_ResponseSyntax) **   <a name="robomaker-DescribeSimulationJobBatch-response-createdAt"></a>
The time, in milliseconds since the epoch, when the simulation job batch was created\.  
Type: Timestamp

 ** [createdRequests](#API_DescribeSimulationJobBatch_ResponseSyntax) **   <a name="robomaker-DescribeSimulationJobBatch-response-createdRequests"></a>
A list of created simulation job summaries\.  
Type: Array of [SimulationJobSummary](API_SimulationJobSummary.md) objects  
Array Members: Minimum number of 0 items\. Maximum number of 100 items\.

 ** [failedRequests](#API_DescribeSimulationJobBatch_ResponseSyntax) **   <a name="robomaker-DescribeSimulationJobBatch-response-failedRequests"></a>
A list of failed create simulation job requests\. The request failed to be created into a simulation job\. Failed requests do not have a simulation job ID\.   
Type: Array of [FailedCreateSimulationJobRequest](API_FailedCreateSimulationJobRequest.md) objects

 ** [failureCode](#API_DescribeSimulationJobBatch_ResponseSyntax) **   <a name="robomaker-DescribeSimulationJobBatch-response-failureCode"></a>
The failure code of the simulation job batch\.  
Type: String  
Valid Values:` InternalServiceError` 

 ** [failureReason](#API_DescribeSimulationJobBatch_ResponseSyntax) **   <a name="robomaker-DescribeSimulationJobBatch-response-failureReason"></a>
The reason the simulation job batch failed\.  
Type: String  
Length Constraints: Minimum length of 0\. Maximum length of 1024\.  
Pattern: `.*` 

 ** [lastUpdatedAt](#API_DescribeSimulationJobBatch_ResponseSyntax) **   <a name="robomaker-DescribeSimulationJobBatch-response-lastUpdatedAt"></a>
The time, in milliseconds since the epoch, when the simulation job batch was last updated\.  
Type: Timestamp

 ** [pendingRequests](#API_DescribeSimulationJobBatch_ResponseSyntax) **   <a name="robomaker-DescribeSimulationJobBatch-response-pendingRequests"></a>
A list of pending simulation job requests\. These requests have not yet been created into simulation jobs\.  
Type: Array of [SimulationJobRequest](API_SimulationJobRequest.md) objects  
Array Members: Minimum number of 1 item\. Maximum number of 1000 items\.

 ** [status](#API_DescribeSimulationJobBatch_ResponseSyntax) **   <a name="robomaker-DescribeSimulationJobBatch-response-status"></a>
The status of the batch\.    
Pending  
The simulation job batch request is pending\.  
InProgress  
The simulation job batch is in progress\.   
Failed  
The simulation job batch failed\. One or more simulation job requests could not be completed due to an internal failure \(like `InternalServiceError`\)\. See `failureCode` and `failureReason` for more information\.  
Completed  
The simulation batch job completed\. A batch is complete when \(1\) there are no pending simulation job requests in the batch and none of the failed simulation job requests are due to `InternalServiceError` and \(2\) when all created simulation jobs have reached a terminal state \(for example, `Completed` or `Failed`\)\.   
Canceled  
The simulation batch job was cancelled\.  
Canceling  
The simulation batch job is being cancelled\.  
Completing  
The simulation batch job is completing\.  
TimingOut  
The simulation job batch is timing out\.  
If a batch timing out, and there are pending requests that were failing due to an internal failure \(like `InternalServiceError`\), the batch status will be `Failed`\. If there are no such failing request, the batch status will be `TimedOut`\.   
TimedOut  
The simulation batch job timed out\.
Type: String  
Valid Values:` Pending | InProgress | Failed | Completed | Canceled | Canceling | Completing | TimingOut | TimedOut` 

 ** [tags](#API_DescribeSimulationJobBatch_ResponseSyntax) **   <a name="robomaker-DescribeSimulationJobBatch-response-tags"></a>
A map that contains tag keys and tag values that are attached to the simulation job batch\.  
Type: String to string map  
Map Entries: Minimum number of 0 items\. Maximum number of 50 items\.  
Key Length Constraints: Minimum length of 1\. Maximum length of 128\.  
Key Pattern: `[a-zA-Z0-9 _.\-\/+=:]*`   
Value Length Constraints: Minimum length of 0\. Maximum length of 256\.  
Value Pattern: `[a-zA-Z0-9 _.\-\/+=:]*` 

## Errors<a name="API_DescribeSimulationJobBatch_Errors"></a>

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

## See Also<a name="API_DescribeSimulationJobBatch_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/robomaker-2018-06-29/DescribeSimulationJobBatch) 
+  [AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/robomaker-2018-06-29/DescribeSimulationJobBatch) 
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/robomaker-2018-06-29/DescribeSimulationJobBatch) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/robomaker-2018-06-29/DescribeSimulationJobBatch) 
+  [AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/robomaker-2018-06-29/DescribeSimulationJobBatch) 
+  [AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/robomaker-2018-06-29/DescribeSimulationJobBatch) 
+  [AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/robomaker-2018-06-29/DescribeSimulationJobBatch) 
+  [AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/robomaker-2018-06-29/DescribeSimulationJobBatch) 
+  [AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/robomaker-2018-06-29/DescribeSimulationJobBatch) 