# GetWorldTemplateBody<a name="API_GetWorldTemplateBody"></a>

Gets the world template body\.

## Request Syntax<a name="API_GetWorldTemplateBody_RequestSyntax"></a>

```
POST /getWorldTemplateBody HTTP/1.1
Content-type: application/json

{
   "generationJob": "string",
   "template": "string"
}
```

## URI Request Parameters<a name="API_GetWorldTemplateBody_RequestParameters"></a>

The request does not use any URI parameters\.

## Request Body<a name="API_GetWorldTemplateBody_RequestBody"></a>

The request accepts the following data in JSON format\.

 ** [generationJob](#API_GetWorldTemplateBody_RequestSyntax) **   <a name="robomaker-GetWorldTemplateBody-request-generationJob"></a>
The Amazon Resource Name \(arn\) of the world generator job\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 1224\.  
Pattern: `arn:.*`   
Required: No

 ** [template](#API_GetWorldTemplateBody_RequestSyntax) **   <a name="robomaker-GetWorldTemplateBody-request-template"></a>
The Amazon Resource Name \(arn\) of the world template\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 1224\.  
Pattern: `arn:.*`   
Required: No

## Response Syntax<a name="API_GetWorldTemplateBody_ResponseSyntax"></a>

```
HTTP/1.1 200
Content-type: application/json

{
   "templateBody": "string"
}
```

## Response Elements<a name="API_GetWorldTemplateBody_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 200 response\.

The following data is returned in JSON format by the service\.

 ** [templateBody](#API_GetWorldTemplateBody_ResponseSyntax) **   <a name="robomaker-GetWorldTemplateBody-response-templateBody"></a>
The world template body\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 262144\.  
Pattern: `[\S\s]+` 

## Errors<a name="API_GetWorldTemplateBody_Errors"></a>

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

## See Also<a name="API_GetWorldTemplateBody_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/robomaker-2018-06-29/GetWorldTemplateBody) 
+  [AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/robomaker-2018-06-29/GetWorldTemplateBody) 
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/robomaker-2018-06-29/GetWorldTemplateBody) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/robomaker-2018-06-29/GetWorldTemplateBody) 
+  [AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/robomaker-2018-06-29/GetWorldTemplateBody) 
+  [AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/robomaker-2018-06-29/GetWorldTemplateBody) 
+  [AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/robomaker-2018-06-29/GetWorldTemplateBody) 
+  [AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/robomaker-2018-06-29/GetWorldTemplateBody) 
+  [AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/robomaker-2018-06-29/GetWorldTemplateBody) 