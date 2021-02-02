# TemplateLocation<a name="API_TemplateLocation"></a>

Information about a template location\.

## Contents<a name="API_TemplateLocation_Contents"></a>

 **s3Bucket**   <a name="robomaker-Type-TemplateLocation-s3Bucket"></a>
The Amazon S3 bucket name\.  
Type: String  
Length Constraints: Minimum length of 3\. Maximum length of 63\.  
Pattern: `[a-z0-9][a-z0-9.\-]*[a-z0-9]`   
Required: Yes

 **s3Key**   <a name="robomaker-Type-TemplateLocation-s3Key"></a>
The list of S3 keys identifying the data source files\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 1024\.  
Pattern: `.*`   
Required: Yes

## See Also<a name="API_TemplateLocation_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/robomaker-2018-06-29/TemplateLocation) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/robomaker-2018-06-29/TemplateLocation) 
+  [AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/robomaker-2018-06-29/TemplateLocation) 
+  [AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/robomaker-2018-06-29/TemplateLocation) 