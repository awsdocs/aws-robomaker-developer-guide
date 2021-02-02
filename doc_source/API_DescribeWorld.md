# DescribeWorld<a name="API_DescribeWorld"></a>

Describes a world\.

## Request Syntax<a name="API_DescribeWorld_RequestSyntax"></a>

```
POST /describeWorld HTTP/1.1
Content-type: application/json

{
   "world": "string"
}
```

## URI Request Parameters<a name="API_DescribeWorld_RequestParameters"></a>

The request does not use any URI parameters\.

## Request Body<a name="API_DescribeWorld_RequestBody"></a>

The request accepts the following data in JSON format\.

 ** [world](#API_DescribeWorld_RequestSyntax) **   <a name="robomaker-DescribeWorld-request-world"></a>
The Amazon Resource Name \(arn\) of the world you want to describe\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 1224\.  
Pattern: `arn:.*`   
Required: Yes

## Response Syntax<a name="API_DescribeWorld_ResponseSyntax"></a>

```
HTTP/1.1 200
Content-type: application/json

{
   "arn": "string",
   "createdAt": number,
   "generationJob": "string",
   "tags": { 
      "string" : "string" 
   },
   "template": "string"
}
```

## Response Elements<a name="API_DescribeWorld_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 200 response\.

The following data is returned in JSON format by the service\.

 ** [arn](#API_DescribeWorld_ResponseSyntax) **   <a name="robomaker-DescribeWorld-response-arn"></a>
The Amazon Resource Name \(arn\) of the world\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 1224\.  
Pattern: `arn:.*` 

 ** [createdAt](#API_DescribeWorld_ResponseSyntax) **   <a name="robomaker-DescribeWorld-response-createdAt"></a>
The time, in milliseconds since the epoch, when the world was created\.  
Type: Timestamp

 ** [generationJob](#API_DescribeWorld_ResponseSyntax) **   <a name="robomaker-DescribeWorld-response-generationJob"></a>
The Amazon Resource Name \(arn\) of the world generation job that generated the world\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 1224\.  
Pattern: `arn:.*` 

 ** [tags](#API_DescribeWorld_ResponseSyntax) **   <a name="robomaker-DescribeWorld-response-tags"></a>
A map that contains tag keys and tag values that are attached to the world\.  
Type: String to string map  
Map Entries: Minimum number of 0 items\. Maximum number of 50 items\.  
Key Length Constraints: Minimum length of 1\. Maximum length of 128\.  
Key Pattern: `[a-zA-Z0-9 _.\-\/+=:]*`   
Value Length Constraints: Minimum length of 0\. Maximum length of 256\.  
Value Pattern: `[a-zA-Z0-9 _.\-\/+=:]*` 

 ** [template](#API_DescribeWorld_ResponseSyntax) **   <a name="robomaker-DescribeWorld-response-template"></a>
The world template\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 1224\.  
Pattern: `arn:.*` 

## Errors<a name="API_DescribeWorld_Errors"></a>

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

## See Also<a name="API_DescribeWorld_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/robomaker-2018-06-29/DescribeWorld) 
+  [AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/robomaker-2018-06-29/DescribeWorld) 
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/robomaker-2018-06-29/DescribeWorld) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/robomaker-2018-06-29/DescribeWorld) 
+  [AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/robomaker-2018-06-29/DescribeWorld) 
+  [AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/robomaker-2018-06-29/DescribeWorld) 
+  [AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/robomaker-2018-06-29/DescribeWorld) 
+  [AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/robomaker-2018-06-29/DescribeWorld) 
+  [AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/robomaker-2018-06-29/DescribeWorld) 