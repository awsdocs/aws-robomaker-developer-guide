# DescribeWorldExportJob<a name="API_DescribeWorldExportJob"></a>

Describes a world export job\.

## Request Syntax<a name="API_DescribeWorldExportJob_RequestSyntax"></a>

```
POST /describeWorldExportJob HTTP/1.1
Content-type: application/json

{
   "job": "string"
}
```

## URI Request Parameters<a name="API_DescribeWorldExportJob_RequestParameters"></a>

The request does not use any URI parameters\.

## Request Body<a name="API_DescribeWorldExportJob_RequestBody"></a>

The request accepts the following data in JSON format\.

 ** [job](#API_DescribeWorldExportJob_RequestSyntax) **   <a name="robomaker-DescribeWorldExportJob-request-job"></a>
The Amazon Resource Name \(arn\) of the world export job to describe\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 1224\.  
Pattern: `arn:.*`   
Required: Yes

## Response Syntax<a name="API_DescribeWorldExportJob_ResponseSyntax"></a>

```
HTTP/1.1 200
Content-type: application/json

{
   "arn": "string",
   "clientRequestToken": "string",
   "createdAt": number,
   "failureCode": "string",
   "failureReason": "string",
   "iamRole": "string",
   "outputLocation": { 
      "s3Bucket": "string",
      "s3Prefix": "string"
   },
   "status": "string",
   "tags": { 
      "string" : "string" 
   },
   "worlds": [ "string" ]
}
```

## Response Elements<a name="API_DescribeWorldExportJob_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 200 response\.

The following data is returned in JSON format by the service\.

 ** [arn](#API_DescribeWorldExportJob_ResponseSyntax) **   <a name="robomaker-DescribeWorldExportJob-response-arn"></a>
The Amazon Resource Name \(ARN\) of the world export job\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 1224\.  
Pattern: `arn:.*` 

 ** [clientRequestToken](#API_DescribeWorldExportJob_ResponseSyntax) **   <a name="robomaker-DescribeWorldExportJob-response-clientRequestToken"></a>
Unique, case\-sensitive identifier that you provide to ensure the idempotency of the request\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 64\.  
Pattern: `[a-zA-Z0-9_\-=]*` 

 ** [createdAt](#API_DescribeWorldExportJob_ResponseSyntax) **   <a name="robomaker-DescribeWorldExportJob-response-createdAt"></a>
The time, in milliseconds since the epoch, when the world export job was created\.  
Type: Timestamp

 ** [failureCode](#API_DescribeWorldExportJob_ResponseSyntax) **   <a name="robomaker-DescribeWorldExportJob-response-failureCode"></a>
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
Type: String  
Valid Values:` InternalServiceError | LimitExceeded | ResourceNotFound | RequestThrottled | InvalidInput | AccessDenied` 

 ** [failureReason](#API_DescribeWorldExportJob_ResponseSyntax) **   <a name="robomaker-DescribeWorldExportJob-response-failureReason"></a>
The reason why the world export job failed\.  
Type: String  
Length Constraints: Minimum length of 0\. Maximum length of 1024\.  
Pattern: `.*` 

 ** [iamRole](#API_DescribeWorldExportJob_ResponseSyntax) **   <a name="robomaker-DescribeWorldExportJob-response-iamRole"></a>
The IAM role that the world export process uses to access the Amazon S3 bucket and put the export\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 255\.  
Pattern: `arn:aws:iam::\w+:role/.*` 

 ** [outputLocation](#API_DescribeWorldExportJob_ResponseSyntax) **   <a name="robomaker-DescribeWorldExportJob-response-outputLocation"></a>
The output location\.  
Type: [OutputLocation](API_OutputLocation.md) object

 ** [status](#API_DescribeWorldExportJob_ResponseSyntax) **   <a name="robomaker-DescribeWorldExportJob-response-status"></a>
The status of the world export job\.    
Pending  
The world export job request is pending\.  
Running  
The world export job is running\.   
Completed  
The world export job completed\.   
Failed  
The world export job failed\. See `failureCode` and `failureReason` for more information\.   
Canceled  
The world export job was cancelled\.  
Canceling  
The world export job is being cancelled\.
Type: String  
Valid Values:` Pending | Running | Completed | Failed | Canceling | Canceled` 

 ** [tags](#API_DescribeWorldExportJob_ResponseSyntax) **   <a name="robomaker-DescribeWorldExportJob-response-tags"></a>
A map that contains tag keys and tag values that are attached to the world export job\.  
Type: String to string map  
Map Entries: Minimum number of 0 items\. Maximum number of 50 items\.  
Key Length Constraints: Minimum length of 1\. Maximum length of 128\.  
Key Pattern: `[a-zA-Z0-9 _.\-\/+=:]*`   
Value Length Constraints: Minimum length of 0\. Maximum length of 256\.  
Value Pattern: `[a-zA-Z0-9 _.\-\/+=:]*` 

 ** [worlds](#API_DescribeWorldExportJob_ResponseSyntax) **   <a name="robomaker-DescribeWorldExportJob-response-worlds"></a>
A list of Amazon Resource Names \(arns\) that correspond to worlds to be exported\.  
Type: Array of strings  
Array Members: Minimum number of 1 item\. Maximum number of 100 items\.  
Length Constraints: Minimum length of 1\. Maximum length of 1224\.  
Pattern: `arn:.*` 

## Errors<a name="API_DescribeWorldExportJob_Errors"></a>

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

## See Also<a name="API_DescribeWorldExportJob_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/robomaker-2018-06-29/DescribeWorldExportJob) 
+  [AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/robomaker-2018-06-29/DescribeWorldExportJob) 
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/robomaker-2018-06-29/DescribeWorldExportJob) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/robomaker-2018-06-29/DescribeWorldExportJob) 
+  [AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/robomaker-2018-06-29/DescribeWorldExportJob) 
+  [AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/robomaker-2018-06-29/DescribeWorldExportJob) 
+  [AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/robomaker-2018-06-29/DescribeWorldExportJob) 
+  [AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/robomaker-2018-06-29/DescribeWorldExportJob) 
+  [AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/robomaker-2018-06-29/DescribeWorldExportJob) 