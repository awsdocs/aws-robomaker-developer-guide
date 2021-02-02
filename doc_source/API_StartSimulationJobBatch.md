# StartSimulationJobBatch<a name="API_StartSimulationJobBatch"></a>

Starts a new simulation job batch\. The batch is defined using one or more `SimulationJobRequest` objects\. 

## Request Syntax<a name="API_StartSimulationJobBatch_RequestSyntax"></a>

```
POST /startSimulationJobBatch HTTP/1.1
Content-type: application/json

{
   "batchPolicy": { 
      "maxConcurrency": number,
      "timeoutInSeconds": number
   },
   "clientRequestToken": "string",
   "createSimulationJobRequests": [ 
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
   "tags": { 
      "string" : "string" 
   }
}
```

## URI Request Parameters<a name="API_StartSimulationJobBatch_RequestParameters"></a>

The request does not use any URI parameters\.

## Request Body<a name="API_StartSimulationJobBatch_RequestBody"></a>

The request accepts the following data in JSON format\.

 ** [batchPolicy](#API_StartSimulationJobBatch_RequestSyntax) **   <a name="robomaker-StartSimulationJobBatch-request-batchPolicy"></a>
The batch policy\.  
Type: [BatchPolicy](API_BatchPolicy.md) object  
Required: No

 ** [clientRequestToken](#API_StartSimulationJobBatch_RequestSyntax) **   <a name="robomaker-StartSimulationJobBatch-request-clientRequestToken"></a>
Unique, case\-sensitive identifier that you provide to ensure the idempotency of the request\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 64\.  
Pattern: `[a-zA-Z0-9_\-=]*`   
Required: No

 ** [createSimulationJobRequests](#API_StartSimulationJobBatch_RequestSyntax) **   <a name="robomaker-StartSimulationJobBatch-request-createSimulationJobRequests"></a>
A list of simulation job requests to create in the batch\.  
Type: Array of [SimulationJobRequest](API_SimulationJobRequest.md) objects  
Array Members: Minimum number of 1 item\. Maximum number of 1000 items\.  
Required: Yes

 ** [tags](#API_StartSimulationJobBatch_RequestSyntax) **   <a name="robomaker-StartSimulationJobBatch-request-tags"></a>
A map that contains tag keys and tag values that are attached to the deployment job batch\.  
Type: String to string map  
Map Entries: Minimum number of 0 items\. Maximum number of 50 items\.  
Key Length Constraints: Minimum length of 1\. Maximum length of 128\.  
Key Pattern: `[a-zA-Z0-9 _.\-\/+=:]*`   
Value Length Constraints: Minimum length of 0\. Maximum length of 256\.  
Value Pattern: `[a-zA-Z0-9 _.\-\/+=:]*`   
Required: No

## Response Syntax<a name="API_StartSimulationJobBatch_ResponseSyntax"></a>

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

## Response Elements<a name="API_StartSimulationJobBatch_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 200 response\.

The following data is returned in JSON format by the service\.

 ** [arn](#API_StartSimulationJobBatch_ResponseSyntax) **   <a name="robomaker-StartSimulationJobBatch-response-arn"></a>
The Amazon Resource Name \(arn\) of the batch\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 1224\.  
Pattern: `arn:.*` 

 ** [batchPolicy](#API_StartSimulationJobBatch_ResponseSyntax) **   <a name="robomaker-StartSimulationJobBatch-response-batchPolicy"></a>
The batch policy\.  
Type: [BatchPolicy](API_BatchPolicy.md) object

 ** [clientRequestToken](#API_StartSimulationJobBatch_ResponseSyntax) **   <a name="robomaker-StartSimulationJobBatch-response-clientRequestToken"></a>
Unique, case\-sensitive identifier that you provide to ensure the idempotency of the request\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 64\.  
Pattern: `[a-zA-Z0-9_\-=]*` 

 ** [createdAt](#API_StartSimulationJobBatch_ResponseSyntax) **   <a name="robomaker-StartSimulationJobBatch-response-createdAt"></a>
The time, in milliseconds since the epoch, when the simulation job batch was created\.  
Type: Timestamp

 ** [createdRequests](#API_StartSimulationJobBatch_ResponseSyntax) **   <a name="robomaker-StartSimulationJobBatch-response-createdRequests"></a>
A list of created simulation job request summaries\.  
Type: Array of [SimulationJobSummary](API_SimulationJobSummary.md) objects  
Array Members: Minimum number of 0 items\. Maximum number of 100 items\.

 ** [failedRequests](#API_StartSimulationJobBatch_ResponseSyntax) **   <a name="robomaker-StartSimulationJobBatch-response-failedRequests"></a>
A list of failed simulation job requests\. The request failed to be created into a simulation job\. Failed requests do not have a simulation job ID\.   
Type: Array of [FailedCreateSimulationJobRequest](API_FailedCreateSimulationJobRequest.md) objects

 ** [failureCode](#API_StartSimulationJobBatch_ResponseSyntax) **   <a name="robomaker-StartSimulationJobBatch-response-failureCode"></a>
The failure code if the simulation job batch failed\.  
Type: String  
Valid Values:` InternalServiceError` 

 ** [failureReason](#API_StartSimulationJobBatch_ResponseSyntax) **   <a name="robomaker-StartSimulationJobBatch-response-failureReason"></a>
The reason the simulation job batch failed\.  
Type: String  
Length Constraints: Minimum length of 0\. Maximum length of 1024\.  
Pattern: `.*` 

 ** [pendingRequests](#API_StartSimulationJobBatch_ResponseSyntax) **   <a name="robomaker-StartSimulationJobBatch-response-pendingRequests"></a>
A list of pending simulation job requests\. These requests have not yet been created into simulation jobs\.  
Type: Array of [SimulationJobRequest](API_SimulationJobRequest.md) objects  
Array Members: Minimum number of 1 item\. Maximum number of 1000 items\.

 ** [status](#API_StartSimulationJobBatch_ResponseSyntax) **   <a name="robomaker-StartSimulationJobBatch-response-status"></a>
The status of the simulation job batch\.    
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

 ** [tags](#API_StartSimulationJobBatch_ResponseSyntax) **   <a name="robomaker-StartSimulationJobBatch-response-tags"></a>
A map that contains tag keys and tag values that are attached to the deployment job batch\.  
Type: String to string map  
Map Entries: Minimum number of 0 items\. Maximum number of 50 items\.  
Key Length Constraints: Minimum length of 1\. Maximum length of 128\.  
Key Pattern: `[a-zA-Z0-9 _.\-\/+=:]*`   
Value Length Constraints: Minimum length of 0\. Maximum length of 256\.  
Value Pattern: `[a-zA-Z0-9 _.\-\/+=:]*` 

## Errors<a name="API_StartSimulationJobBatch_Errors"></a>

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

 **ThrottlingException**   
AWS RoboMaker is temporarily unable to process the request\. Try your call again\.  
HTTP Status Code: 400

## See Also<a name="API_StartSimulationJobBatch_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/robomaker-2018-06-29/StartSimulationJobBatch) 
+  [AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/robomaker-2018-06-29/StartSimulationJobBatch) 
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/robomaker-2018-06-29/StartSimulationJobBatch) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/robomaker-2018-06-29/StartSimulationJobBatch) 
+  [AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/robomaker-2018-06-29/StartSimulationJobBatch) 
+  [AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/robomaker-2018-06-29/StartSimulationJobBatch) 
+  [AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/robomaker-2018-06-29/StartSimulationJobBatch) 
+  [AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/robomaker-2018-06-29/StartSimulationJobBatch) 
+  [AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/robomaker-2018-06-29/StartSimulationJobBatch) 