# WorldGenerationJobSummary<a name="API_WorldGenerationJobSummary"></a>

Information about a world generator job\.

## Contents<a name="API_WorldGenerationJobSummary_Contents"></a>

 **arn**   <a name="robomaker-Type-WorldGenerationJobSummary-arn"></a>
The Amazon Resource Name \(ARN\) of the world generator job\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 1224\.  
Pattern: `arn:.*`   
Required: No

 **createdAt**   <a name="robomaker-Type-WorldGenerationJobSummary-createdAt"></a>
The time, in milliseconds since the epoch, when the world generator job was created\.  
Type: Timestamp  
Required: No

 **failedWorldCount**   <a name="robomaker-Type-WorldGenerationJobSummary-failedWorldCount"></a>
The number of worlds that failed\.  
Type: Integer  
Required: No

 **status**   <a name="robomaker-Type-WorldGenerationJobSummary-status"></a>
The status of the world generator job:    
Pending  
The world generator job request is pending\.  
Running  
The world generator job is running\.   
Completed  
The world generator job completed\.   
Failed  
The world generator job failed\. See `failureCode` for more information\.   
PartialFailed  
Some worlds did not generate\.  
Canceled  
The world generator job was cancelled\.  
Canceling  
The world generator job is being cancelled\.
Type: String  
Valid Values:` Pending | Running | Completed | Failed | PartialFailed | Canceling | Canceled`   
Required: No

 **succeededWorldCount**   <a name="robomaker-Type-WorldGenerationJobSummary-succeededWorldCount"></a>
The number of worlds that were generated\.  
Type: Integer  
Required: No

 **template**   <a name="robomaker-Type-WorldGenerationJobSummary-template"></a>
The Amazon Resource Name \(arn\) of the world template\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 1224\.  
Pattern: `arn:.*`   
Required: No

 **worldCount**   <a name="robomaker-Type-WorldGenerationJobSummary-worldCount"></a>
Information about the world count\.  
Type: [WorldCount](API_WorldCount.md) object  
Required: No

## See Also<a name="API_WorldGenerationJobSummary_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/robomaker-2018-06-29/WorldGenerationJobSummary) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/robomaker-2018-06-29/WorldGenerationJobSummary) 
+  [AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/robomaker-2018-06-29/WorldGenerationJobSummary) 
+  [AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/robomaker-2018-06-29/WorldGenerationJobSummary) 