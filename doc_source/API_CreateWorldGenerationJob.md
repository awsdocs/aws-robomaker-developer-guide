# CreateWorldGenerationJob<a name="API_CreateWorldGenerationJob"></a>

Creates worlds using the specified template\.

## Request Syntax<a name="API_CreateWorldGenerationJob_RequestSyntax"></a>

```
POST /createWorldGenerationJob HTTP/1.1
Content-type: application/json

{
   "clientRequestToken": "string",
   "tags": { 
      "string" : "string" 
   },
   "template": "string",
   "worldCount": { 
      "floorplanCount": number,
      "interiorCountPerFloorplan": number
   },
   "worldTags": { 
      "string" : "string" 
   }
}
```

## URI Request Parameters<a name="API_CreateWorldGenerationJob_RequestParameters"></a>

The request does not use any URI parameters\.

## Request Body<a name="API_CreateWorldGenerationJob_RequestBody"></a>

The request accepts the following data in JSON format\.

 ** [clientRequestToken](#API_CreateWorldGenerationJob_RequestSyntax) **   <a name="robomaker-CreateWorldGenerationJob-request-clientRequestToken"></a>
Unique, case\-sensitive identifier that you provide to ensure the idempotency of the request\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 64\.  
Pattern: `[a-zA-Z0-9_\-=]*`   
Required: No

 ** [tags](#API_CreateWorldGenerationJob_RequestSyntax) **   <a name="robomaker-CreateWorldGenerationJob-request-tags"></a>
A map that contains tag keys and tag values that are attached to the world generator job\.  
Type: String to string map  
Map Entries: Minimum number of 0 items\. Maximum number of 50 items\.  
Key Length Constraints: Minimum length of 1\. Maximum length of 128\.  
Key Pattern: `[a-zA-Z0-9 _.\-\/+=:]*`   
Value Length Constraints: Minimum length of 0\. Maximum length of 256\.  
Value Pattern: `[a-zA-Z0-9 _.\-\/+=:]*`   
Required: No

 ** [template](#API_CreateWorldGenerationJob_RequestSyntax) **   <a name="robomaker-CreateWorldGenerationJob-request-template"></a>
The Amazon Resource Name \(arn\) of the world template describing the worlds you want to create\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 1224\.  
Pattern: `arn:.*`   
Required: Yes

 ** [worldCount](#API_CreateWorldGenerationJob_RequestSyntax) **   <a name="robomaker-CreateWorldGenerationJob-request-worldCount"></a>
Information about the world count\.  
Type: [WorldCount](API_WorldCount.md) object  
Required: Yes

 ** [worldTags](#API_CreateWorldGenerationJob_RequestSyntax) **   <a name="robomaker-CreateWorldGenerationJob-request-worldTags"></a>
A map that contains tag keys and tag values that are attached to the generated worlds\.  
Type: String to string map  
Map Entries: Minimum number of 0 items\. Maximum number of 50 items\.  
Key Length Constraints: Minimum length of 1\. Maximum length of 128\.  
Key Pattern: `[a-zA-Z0-9 _.\-\/+=:]*`   
Value Length Constraints: Minimum length of 0\. Maximum length of 256\.  
Value Pattern: `[a-zA-Z0-9 _.\-\/+=:]*`   
Required: No

## Response Syntax<a name="API_CreateWorldGenerationJob_ResponseSyntax"></a>

```
HTTP/1.1 200
Content-type: application/json

{
   "arn": "string",
   "clientRequestToken": "string",
   "createdAt": number,
   "failureCode": "string",
   "status": "string",
   "tags": { 
      "string" : "string" 
   },
   "template": "string",
   "worldCount": { 
      "floorplanCount": number,
      "interiorCountPerFloorplan": number
   },
   "worldTags": { 
      "string" : "string" 
   }
}
```

## Response Elements<a name="API_CreateWorldGenerationJob_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 200 response\.

The following data is returned in JSON format by the service\.

 ** [arn](#API_CreateWorldGenerationJob_ResponseSyntax) **   <a name="robomaker-CreateWorldGenerationJob-response-arn"></a>
The Amazon Resource Name \(ARN\) of the world generator job\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 1224\.  
Pattern: `arn:.*` 

 ** [clientRequestToken](#API_CreateWorldGenerationJob_ResponseSyntax) **   <a name="robomaker-CreateWorldGenerationJob-response-clientRequestToken"></a>
Unique, case\-sensitive identifier that you provide to ensure the idempotency of the request\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 64\.  
Pattern: `[a-zA-Z0-9_\-=]*` 

 ** [createdAt](#API_CreateWorldGenerationJob_ResponseSyntax) **   <a name="robomaker-CreateWorldGenerationJob-response-createdAt"></a>
The time, in milliseconds since the epoch, when the world generator job was created\.  
Type: Timestamp

 ** [failureCode](#API_CreateWorldGenerationJob_ResponseSyntax) **   <a name="robomaker-CreateWorldGenerationJob-response-failureCode"></a>
The failure code of the world generator job if it failed:    
InternalServiceError  
Internal service error\.  
LimitExceeded  
The requested resource exceeds the maximum number allowed, or the number of concurrent stream requests exceeds the maximum number allowed\.   
ResourceNotFound  
The specified resource could not be found\.   
RequestThrottled  
The request was throttled\.  
InvalidInput  
An input parameter in the request is not valid\.
Type: String  
Valid Values:` InternalServiceError | LimitExceeded | ResourceNotFound | RequestThrottled | InvalidInput | AllWorldGenerationFailed` 

 ** [status](#API_CreateWorldGenerationJob_ResponseSyntax) **   <a name="robomaker-CreateWorldGenerationJob-response-status"></a>
The status of the world generator job\.    
Pending  
The world generator job request is pending\.  
Running  
The world generator job is running\.   
Completed  
The world generator job completed\.   
Failed  
The world generator job failed\. See `failureCode` for more information\.   
PartialFailed  
Some worlds did not generate\.  
Canceled  
The world generator job was cancelled\.  
Canceling  
The world generator job is being cancelled\.
Type: String  
Valid Values:` Pending | Running | Completed | Failed | PartialFailed | Canceling | Canceled` 

 ** [tags](#API_CreateWorldGenerationJob_ResponseSyntax) **   <a name="robomaker-CreateWorldGenerationJob-response-tags"></a>
A map that contains tag keys and tag values that are attached to the world generator job\.  
Type: String to string map  
Map Entries: Minimum number of 0 items\. Maximum number of 50 items\.  
Key Length Constraints: Minimum length of 1\. Maximum length of 128\.  
Key Pattern: `[a-zA-Z0-9 _.\-\/+=:]*`   
Value Length Constraints: Minimum length of 0\. Maximum length of 256\.  
Value Pattern: `[a-zA-Z0-9 _.\-\/+=:]*` 

 ** [template](#API_CreateWorldGenerationJob_ResponseSyntax) **   <a name="robomaker-CreateWorldGenerationJob-response-template"></a>
The Amazon Resource Name \(arn\) of the world template\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 1224\.  
Pattern: `arn:.*` 

 ** [worldCount](#API_CreateWorldGenerationJob_ResponseSyntax) **   <a name="robomaker-CreateWorldGenerationJob-response-worldCount"></a>
Information about the world count\.   
Type: [WorldCount](API_WorldCount.md) object

 ** [worldTags](#API_CreateWorldGenerationJob_ResponseSyntax) **   <a name="robomaker-CreateWorldGenerationJob-response-worldTags"></a>
A map that contains tag keys and tag values that are attached to the generated worlds\.  
Type: String to string map  
Map Entries: Minimum number of 0 items\. Maximum number of 50 items\.  
Key Length Constraints: Minimum length of 1\. Maximum length of 128\.  
Key Pattern: `[a-zA-Z0-9 _.\-\/+=:]*`   
Value Length Constraints: Minimum length of 0\. Maximum length of 256\.  
Value Pattern: `[a-zA-Z0-9 _.\-\/+=:]*` 

## Errors<a name="API_CreateWorldGenerationJob_Errors"></a>

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

## See Also<a name="API_CreateWorldGenerationJob_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/robomaker-2018-06-29/CreateWorldGenerationJob) 
+  [AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/robomaker-2018-06-29/CreateWorldGenerationJob) 
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/robomaker-2018-06-29/CreateWorldGenerationJob) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/robomaker-2018-06-29/CreateWorldGenerationJob) 
+  [AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/robomaker-2018-06-29/CreateWorldGenerationJob) 
+  [AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/robomaker-2018-06-29/CreateWorldGenerationJob) 
+  [AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/robomaker-2018-06-29/CreateWorldGenerationJob) 
+  [AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/robomaker-2018-06-29/CreateWorldGenerationJob) 
+  [AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/robomaker-2018-06-29/CreateWorldGenerationJob) 