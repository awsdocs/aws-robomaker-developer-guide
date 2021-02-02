# CancelWorldExportJob<a name="API_CancelWorldExportJob"></a>

Cancels the specified export job\.

## Request Syntax<a name="API_CancelWorldExportJob_RequestSyntax"></a>

```
POST /cancelWorldExportJob HTTP/1.1
Content-type: application/json

{
   "job": "string"
}
```

## URI Request Parameters<a name="API_CancelWorldExportJob_RequestParameters"></a>

The request does not use any URI parameters\.

## Request Body<a name="API_CancelWorldExportJob_RequestBody"></a>

The request accepts the following data in JSON format\.

 ** [job](#API_CancelWorldExportJob_RequestSyntax) **   <a name="robomaker-CancelWorldExportJob-request-job"></a>
The Amazon Resource Name \(arn\) of the world export job to cancel\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 1224\.  
Pattern: `arn:.*`   
Required: Yes

## Response Syntax<a name="API_CancelWorldExportJob_ResponseSyntax"></a>

```
HTTP/1.1 200
```

## Response Elements<a name="API_CancelWorldExportJob_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 200 response with an empty HTTP body\.

## Errors<a name="API_CancelWorldExportJob_Errors"></a>

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

## See Also<a name="API_CancelWorldExportJob_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/robomaker-2018-06-29/CancelWorldExportJob) 
+  [AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/robomaker-2018-06-29/CancelWorldExportJob) 
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/robomaker-2018-06-29/CancelWorldExportJob) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/robomaker-2018-06-29/CancelWorldExportJob) 
+  [AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/robomaker-2018-06-29/CancelWorldExportJob) 
+  [AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/robomaker-2018-06-29/CancelWorldExportJob) 
+  [AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/robomaker-2018-06-29/CancelWorldExportJob) 
+  [AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/robomaker-2018-06-29/CancelWorldExportJob) 
+  [AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/robomaker-2018-06-29/CancelWorldExportJob) 