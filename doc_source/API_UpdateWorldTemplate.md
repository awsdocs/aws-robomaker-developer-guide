# UpdateWorldTemplate<a name="API_UpdateWorldTemplate"></a>

Updates a world template\.

## Request Syntax<a name="API_UpdateWorldTemplate_RequestSyntax"></a>

```
POST /updateWorldTemplate HTTP/1.1
Content-type: application/json

{
   "name": "string",
   "template": "string",
   "templateBody": "string",
   "templateLocation": { 
      "s3Bucket": "string",
      "s3Key": "string"
   }
}
```

## URI Request Parameters<a name="API_UpdateWorldTemplate_RequestParameters"></a>

The request does not use any URI parameters\.

## Request Body<a name="API_UpdateWorldTemplate_RequestBody"></a>

The request accepts the following data in JSON format\.

 ** [name](#API_UpdateWorldTemplate_RequestSyntax) **   <a name="robomaker-UpdateWorldTemplate-request-name"></a>
The name of the template\.  
Type: String  
Length Constraints: Minimum length of 0\. Maximum length of 255\.  
Pattern: `.*`   
Required: No

 ** [template](#API_UpdateWorldTemplate_RequestSyntax) **   <a name="robomaker-UpdateWorldTemplate-request-template"></a>
The Amazon Resource Name \(arn\) of the world template to update\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 1224\.  
Pattern: `arn:.*`   
Required: Yes

 ** [templateBody](#API_UpdateWorldTemplate_RequestSyntax) **   <a name="robomaker-UpdateWorldTemplate-request-templateBody"></a>
The world template body\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 262144\.  
Pattern: `[\S\s]+`   
Required: No

 ** [templateLocation](#API_UpdateWorldTemplate_RequestSyntax) **   <a name="robomaker-UpdateWorldTemplate-request-templateLocation"></a>
The location of the world template\.  
Type: [TemplateLocation](API_TemplateLocation.md) object  
Required: No

## Response Syntax<a name="API_UpdateWorldTemplate_ResponseSyntax"></a>

```
HTTP/1.1 200
Content-type: application/json

{
   "arn": "string",
   "createdAt": number,
   "lastUpdatedAt": number,
   "name": "string"
}
```

## Response Elements<a name="API_UpdateWorldTemplate_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 200 response\.

The following data is returned in JSON format by the service\.

 ** [arn](#API_UpdateWorldTemplate_ResponseSyntax) **   <a name="robomaker-UpdateWorldTemplate-response-arn"></a>
The Amazon Resource Name \(arn\) of the world template\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 1224\.  
Pattern: `arn:.*` 

 ** [createdAt](#API_UpdateWorldTemplate_ResponseSyntax) **   <a name="robomaker-UpdateWorldTemplate-response-createdAt"></a>
The time, in milliseconds since the epoch, when the world template was created\.  
Type: Timestamp

 ** [lastUpdatedAt](#API_UpdateWorldTemplate_ResponseSyntax) **   <a name="robomaker-UpdateWorldTemplate-response-lastUpdatedAt"></a>
The time, in milliseconds since the epoch, when the world template was last updated\.  
Type: Timestamp

 ** [name](#API_UpdateWorldTemplate_ResponseSyntax) **   <a name="robomaker-UpdateWorldTemplate-response-name"></a>
The name of the world template\.  
Type: String  
Length Constraints: Minimum length of 0\. Maximum length of 255\.  
Pattern: `.*` 

## Errors<a name="API_UpdateWorldTemplate_Errors"></a>

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

## See Also<a name="API_UpdateWorldTemplate_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/robomaker-2018-06-29/UpdateWorldTemplate) 
+  [AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/robomaker-2018-06-29/UpdateWorldTemplate) 
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/robomaker-2018-06-29/UpdateWorldTemplate) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/robomaker-2018-06-29/UpdateWorldTemplate) 
+  [AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/robomaker-2018-06-29/UpdateWorldTemplate) 
+  [AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/robomaker-2018-06-29/UpdateWorldTemplate) 
+  [AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/robomaker-2018-06-29/UpdateWorldTemplate) 
+  [AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/robomaker-2018-06-29/UpdateWorldTemplate) 
+  [AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/robomaker-2018-06-29/UpdateWorldTemplate) 