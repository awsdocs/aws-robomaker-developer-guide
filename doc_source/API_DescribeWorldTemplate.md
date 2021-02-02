# DescribeWorldTemplate<a name="API_DescribeWorldTemplate"></a>

Describes a world template\.

## Request Syntax<a name="API_DescribeWorldTemplate_RequestSyntax"></a>

```
POST /describeWorldTemplate HTTP/1.1
Content-type: application/json

{
   "template": "string"
}
```

## URI Request Parameters<a name="API_DescribeWorldTemplate_RequestParameters"></a>

The request does not use any URI parameters\.

## Request Body<a name="API_DescribeWorldTemplate_RequestBody"></a>

The request accepts the following data in JSON format\.

 ** [template](#API_DescribeWorldTemplate_RequestSyntax) **   <a name="robomaker-DescribeWorldTemplate-request-template"></a>
The Amazon Resource Name \(arn\) of the world template you want to describe\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 1224\.  
Pattern: `arn:.*`   
Required: Yes

## Response Syntax<a name="API_DescribeWorldTemplate_ResponseSyntax"></a>

```
HTTP/1.1 200
Content-type: application/json

{
   "arn": "string",
   "clientRequestToken": "string",
   "createdAt": number,
   "lastUpdatedAt": number,
   "name": "string",
   "tags": { 
      "string" : "string" 
   }
}
```

## Response Elements<a name="API_DescribeWorldTemplate_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 200 response\.

The following data is returned in JSON format by the service\.

 ** [arn](#API_DescribeWorldTemplate_ResponseSyntax) **   <a name="robomaker-DescribeWorldTemplate-response-arn"></a>
The Amazon Resource Name \(ARN\) of the world template\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 1224\.  
Pattern: `arn:.*` 

 ** [clientRequestToken](#API_DescribeWorldTemplate_ResponseSyntax) **   <a name="robomaker-DescribeWorldTemplate-response-clientRequestToken"></a>
Unique, case\-sensitive identifier that you provide to ensure the idempotency of the request\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 64\.  
Pattern: `[a-zA-Z0-9_\-=]*` 

 ** [createdAt](#API_DescribeWorldTemplate_ResponseSyntax) **   <a name="robomaker-DescribeWorldTemplate-response-createdAt"></a>
The time, in milliseconds since the epoch, when the world template was created\.  
Type: Timestamp

 ** [lastUpdatedAt](#API_DescribeWorldTemplate_ResponseSyntax) **   <a name="robomaker-DescribeWorldTemplate-response-lastUpdatedAt"></a>
The time, in milliseconds since the epoch, when the world template was last updated\.  
Type: Timestamp

 ** [name](#API_DescribeWorldTemplate_ResponseSyntax) **   <a name="robomaker-DescribeWorldTemplate-response-name"></a>
The name of the world template\.  
Type: String  
Length Constraints: Minimum length of 0\. Maximum length of 255\.  
Pattern: `.*` 

 ** [tags](#API_DescribeWorldTemplate_ResponseSyntax) **   <a name="robomaker-DescribeWorldTemplate-response-tags"></a>
A map that contains tag keys and tag values that are attached to the world template\.  
Type: String to string map  
Map Entries: Minimum number of 0 items\. Maximum number of 50 items\.  
Key Length Constraints: Minimum length of 1\. Maximum length of 128\.  
Key Pattern: `[a-zA-Z0-9 _.\-\/+=:]*`   
Value Length Constraints: Minimum length of 0\. Maximum length of 256\.  
Value Pattern: `[a-zA-Z0-9 _.\-\/+=:]*` 

## Errors<a name="API_DescribeWorldTemplate_Errors"></a>

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

## See Also<a name="API_DescribeWorldTemplate_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/robomaker-2018-06-29/DescribeWorldTemplate) 
+  [AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/robomaker-2018-06-29/DescribeWorldTemplate) 
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/robomaker-2018-06-29/DescribeWorldTemplate) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/robomaker-2018-06-29/DescribeWorldTemplate) 
+  [AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/robomaker-2018-06-29/DescribeWorldTemplate) 
+  [AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/robomaker-2018-06-29/DescribeWorldTemplate) 
+  [AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/robomaker-2018-06-29/DescribeWorldTemplate) 
+  [AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/robomaker-2018-06-29/DescribeWorldTemplate) 
+  [AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/robomaker-2018-06-29/DescribeWorldTemplate) 