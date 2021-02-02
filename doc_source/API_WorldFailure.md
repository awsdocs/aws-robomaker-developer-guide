# WorldFailure<a name="API_WorldFailure"></a>

Information about a failed world\.

## Contents<a name="API_WorldFailure_Contents"></a>

 **failureCode**   <a name="robomaker-Type-WorldFailure-failureCode"></a>
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
Valid Values:` InternalServiceError | LimitExceeded | ResourceNotFound | RequestThrottled | InvalidInput | AllWorldGenerationFailed`   
Required: No

 **failureCount**   <a name="robomaker-Type-WorldFailure-failureCount"></a>
The number of failed worlds\.  
Type: Integer  
Required: No

 **sampleFailureReason**   <a name="robomaker-Type-WorldFailure-sampleFailureReason"></a>
The sample reason why the world failed\. World errors are aggregated\. A sample is used as the `sampleFailureReason`\.   
Type: String  
Length Constraints: Minimum length of 0\. Maximum length of 1024\.  
Pattern: `.*`   
Required: No

## See Also<a name="API_WorldFailure_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/robomaker-2018-06-29/WorldFailure) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/robomaker-2018-06-29/WorldFailure) 
+  [AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/robomaker-2018-06-29/WorldFailure) 
+  [AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/robomaker-2018-06-29/WorldFailure) 