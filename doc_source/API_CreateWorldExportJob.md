# CreateWorldExportJob<a name="API_CreateWorldExportJob"></a>

Creates a world export job\.

## Request Syntax<a name="API_CreateWorldExportJob_RequestSyntax"></a>

```
POST /createWorldExportJob HTTP/1.1
Content-type: application/json

{
   "clientRequestToken": "string",
   "iamRole": "string",
   "outputLocation": { 
      "s3Bucket": "string",
      "s3Prefix": "string"
   },
   "tags": { 
      "string" : "string" 
   },
   "worlds": [ "string" ]
}
```

## URI Request Parameters<a name="API_CreateWorldExportJob_RequestParameters"></a>

The request does not use any URI parameters\.

## Request Body<a name="API_CreateWorldExportJob_RequestBody"></a>

The request accepts the following data in JSON format\.

 ** [clientRequestToken](#API_CreateWorldExportJob_RequestSyntax) **   <a name="robomaker-CreateWorldExportJob-request-clientRequestToken"></a>
Unique, case\-sensitive identifier that you provide to ensure the idempotency of the request\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 64\.  
Pattern: `[a-zA-Z0-9_\-=]*`   
Required: No

 ** [iamRole](#API_CreateWorldExportJob_RequestSyntax) **   <a name="robomaker-CreateWorldExportJob-request-iamRole"></a>
The IAM role that the world export process uses to access the Amazon S3 bucket and put the export\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 255\.  
Pattern: `arn:aws:iam::\w+:role/.*`   
Required: Yes

 ** [outputLocation](#API_CreateWorldExportJob_RequestSyntax) **   <a name="robomaker-CreateWorldExportJob-request-outputLocation"></a>
The output location\.  
Type: [OutputLocation](API_OutputLocation.md) object  
Required: Yes

 ** [tags](#API_CreateWorldExportJob_RequestSyntax) **   <a name="robomaker-CreateWorldExportJob-request-tags"></a>
A map that contains tag keys and tag values that are attached to the world export job\.  
Type: String to string map  
Map Entries: Minimum number of 0 items\. Maximum number of 50 items\.  
Key Length Constraints: Minimum length of 1\. Maximum length of 128\.  
Key Pattern: `[a-zA-Z0-9 _.\-\/+=:]*`   
Value Length Constraints: Minimum length of 0\. Maximum length of 256\.  
Value Pattern: `[a-zA-Z0-9 _.\-\/+=:]*`   
Required: No

 ** [worlds](#API_CreateWorldExportJob_RequestSyntax) **   <a name="robomaker-CreateWorldExportJob-request-worlds"></a>
A list of Amazon Resource Names \(arns\) that correspond to worlds to export\.  
Type: Array of strings  
Array Members: Minimum number of 1 item\. Maximum number of 100 items\.  
Length Constraints: Minimum length of 1\. Maximum length of 1224\.  
Pattern: `arn:.*`   
Required: Yes

## Response Syntax<a name="API_CreateWorldExportJob_ResponseSyntax"></a>

```
HTTP/1.1 200
Content-type: application/json

{
   "arn": "string",
   "clientRequestToken": "string",
   "createdAt": number,
   "failureCode": "string",
   "iamRole": "string",
   "outputLocation": { 
      "s3Bucket": "string",
      "s3Prefix": "string"
   },
   "status": "string",
   "tags": { 
      "string" : "string" 
   }
}
```

## Response Elements<a name="API_CreateWorldExportJob_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 200 response\.

The following data is returned in JSON format by the service\.

 ** [arn](#API_CreateWorldExportJob_ResponseSyntax) **   <a name="robomaker-CreateWorldExportJob-response-arn"></a>
The Amazon Resource Name \(ARN\) of the world export job\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 1224\.  
Pattern: `arn:.*` 

 ** [clientRequestToken](#API_CreateWorldExportJob_ResponseSyntax) **   <a name="robomaker-CreateWorldExportJob-response-clientRequestToken"></a>
Unique, case\-sensitive identifier that you provide to ensure the idempotency of the request\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 64\.  
Pattern: `[a-zA-Z0-9_\-=]*` 

 ** [createdAt](#API_CreateWorldExportJob_ResponseSyntax) **   <a name="robomaker-CreateWorldExportJob-response-createdAt"></a>
The time, in milliseconds since the epoch, when the world export job was created\.  
Type: Timestamp

 ** [failureCode](#API_CreateWorldExportJob_ResponseSyntax) **   <a name="robomaker-CreateWorldExportJob-response-failureCode"></a>
The failure code of the world export job if it failed:    
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
AllWorldGenerationFailed  
All of the worlds in the world generation job failed\. This can happen if your `worldCount` is greater than 50 or less than 1\. 
For more information about troubleshooting WorldForge, see [Troubleshooting Simulation WorldForge](https://docs.aws.amazon.com/robomaker/latest/dg/troubleshooting-worldforge.html)\.   
Type: String  
Valid Values:` InternalServiceError | LimitExceeded | ResourceNotFound | RequestThrottled | InvalidInput | AccessDenied` 

 ** [iamRole](#API_CreateWorldExportJob_ResponseSyntax) **   <a name="robomaker-CreateWorldExportJob-response-iamRole"></a>
The IAM role that the world export process uses to access the Amazon S3 bucket and put the export\.   
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 255\.  
Pattern: `arn:aws:iam::\w+:role/.*` 

 ** [outputLocation](#API_CreateWorldExportJob_ResponseSyntax) **   <a name="robomaker-CreateWorldExportJob-response-outputLocation"></a>
The output location\.  
Type: [OutputLocation](API_OutputLocation.md) object

 ** [status](#API_CreateWorldExportJob_ResponseSyntax) **   <a name="robomaker-CreateWorldExportJob-response-status"></a>
The status of the world export job\.    
Pending  
The world export job request is pending\.  
Running  
The world export job is running\.   
Completed  
The world export job completed\.   
Failed  
The world export job failed\. See `failureCode` for more information\.   
Canceled  
The world export job was cancelled\.  
Canceling  
The world export job is being cancelled\.
Type: String  
Valid Values:` Pending | Running | Completed | Failed | Canceling | Canceled` 

 ** [tags](#API_CreateWorldExportJob_ResponseSyntax) **   <a name="robomaker-CreateWorldExportJob-response-tags"></a>
A map that contains tag keys and tag values that are attached to the world export job\.  
Type: String to string map  
Map Entries: Minimum number of 0 items\. Maximum number of 50 items\.  
Key Length Constraints: Minimum length of 1\. Maximum length of 128\.  
Key Pattern: `[a-zA-Z0-9 _.\-\/+=:]*`   
Value Length Constraints: Minimum length of 0\. Maximum length of 256\.  
Value Pattern: `[a-zA-Z0-9 _.\-\/+=:]*` 

## Errors<a name="API_CreateWorldExportJob_Errors"></a>

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

 **ResourceNotFoundException**   
The specified resource does not exist\.  
HTTP Status Code: 400

 **ServiceUnavailableException**   
The request has failed due to a temporary failure of the server\.  
HTTP Status Code: 503

 **ThrottlingException**   
AWS RoboMaker is temporarily unable to process the request\. Try your call again\.  
HTTP Status Code: 400

## See Also<a name="API_CreateWorldExportJob_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/robomaker-2018-06-29/CreateWorldExportJob) 
+  [AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/robomaker-2018-06-29/CreateWorldExportJob) 
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/robomaker-2018-06-29/CreateWorldExportJob) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/robomaker-2018-06-29/CreateWorldExportJob) 
+  [AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/robomaker-2018-06-29/CreateWorldExportJob) 
+  [AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/robomaker-2018-06-29/CreateWorldExportJob) 
+  [AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/robomaker-2018-06-29/CreateWorldExportJob) 
+  [AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/robomaker-2018-06-29/CreateWorldExportJob) 
+  [AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/robomaker-2018-06-29/CreateWorldExportJob) 