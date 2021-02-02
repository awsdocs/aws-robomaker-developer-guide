# ListWorldTemplates<a name="API_ListWorldTemplates"></a>

Lists world templates\.

## Request Syntax<a name="API_ListWorldTemplates_RequestSyntax"></a>

```
POST /listWorldTemplates HTTP/1.1
Content-type: application/json

{
   "maxResults": number,
   "nextToken": "string"
}
```

## URI Request Parameters<a name="API_ListWorldTemplates_RequestParameters"></a>

The request does not use any URI parameters\.

## Request Body<a name="API_ListWorldTemplates_RequestBody"></a>

The request accepts the following data in JSON format\.

 ** [maxResults](#API_ListWorldTemplates_RequestSyntax) **   <a name="robomaker-ListWorldTemplates-request-maxResults"></a>
When this parameter is used, `ListWorldTemplates` only returns `maxResults` results in a single page along with a `nextToken` response element\. The remaining results of the initial request can be seen by sending another `ListWorldTemplates` request with the returned `nextToken` value\. This value can be between 1 and 100\. If this parameter is not used, then `ListWorldTemplates` returns up to 100 results and a `nextToken` value if applicable\.   
Type: Integer  
Required: No

 ** [nextToken](#API_ListWorldTemplates_RequestSyntax) **   <a name="robomaker-ListWorldTemplates-request-nextToken"></a>
If the previous paginated request did not return all of the remaining results, the response object's `nextToken` parameter value is set to a token\. To retrieve the next set of results, call `ListWorldTemplates` again and assign that token to the request object's `nextToken` parameter\. If there are no remaining results, the previous response object's NextToken parameter is set to null\.   
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 2048\.  
Pattern: `[a-zA-Z0-9_.\-\/+=]*`   
Required: No

## Response Syntax<a name="API_ListWorldTemplates_ResponseSyntax"></a>

```
HTTP/1.1 200
Content-type: application/json

{
   "nextToken": "string",
   "templateSummaries": [ 
      { 
         "arn": "string",
         "createdAt": number,
         "lastUpdatedAt": number,
         "name": "string"
      }
   ]
}
```

## Response Elements<a name="API_ListWorldTemplates_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 200 response\.

The following data is returned in JSON format by the service\.

 ** [nextToken](#API_ListWorldTemplates_ResponseSyntax) **   <a name="robomaker-ListWorldTemplates-response-nextToken"></a>
If the previous paginated request did not return all of the remaining results, the response object's `nextToken` parameter value is set to a token\. To retrieve the next set of results, call `ListWorldTemplates` again and assign that token to the request object's `nextToken` parameter\. If there are no remaining results, the previous response object's NextToken parameter is set to null\.   
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 2048\.  
Pattern: `[a-zA-Z0-9_.\-\/+=]*` 

 ** [templateSummaries](#API_ListWorldTemplates_ResponseSyntax) **   <a name="robomaker-ListWorldTemplates-response-templateSummaries"></a>
Summary information for templates\.  
Type: Array of [TemplateSummary](API_TemplateSummary.md) objects

## Errors<a name="API_ListWorldTemplates_Errors"></a>

For information about the errors that are common to all actions, see [Common Errors](CommonErrors.md)\.

 **InternalServerException**   
AWS RoboMaker experienced a service issue\. Try your call again\.  
HTTP Status Code: 500

 **InvalidParameterException**   
A parameter specified in a request is not valid, is unsupported, or cannot be used\. The returned message provides an explanation of the error value\.  
HTTP Status Code: 400

 **ThrottlingException**   
AWS RoboMaker is temporarily unable to process the request\. Try your call again\.  
HTTP Status Code: 400

## See Also<a name="API_ListWorldTemplates_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/robomaker-2018-06-29/ListWorldTemplates) 
+  [AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/robomaker-2018-06-29/ListWorldTemplates) 
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/robomaker-2018-06-29/ListWorldTemplates) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/robomaker-2018-06-29/ListWorldTemplates) 
+  [AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/robomaker-2018-06-29/ListWorldTemplates) 
+  [AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/robomaker-2018-06-29/ListWorldTemplates) 
+  [AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/robomaker-2018-06-29/ListWorldTemplates) 
+  [AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/robomaker-2018-06-29/ListWorldTemplates) 
+  [AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/robomaker-2018-06-29/ListWorldTemplates) 