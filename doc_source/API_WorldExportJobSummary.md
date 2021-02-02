# WorldExportJobSummary<a name="API_WorldExportJobSummary"></a>

Information about a world export job\.

## Contents<a name="API_WorldExportJobSummary_Contents"></a>

 **arn**   <a name="robomaker-Type-WorldExportJobSummary-arn"></a>
The Amazon Resource Name \(ARN\) of the world export job\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 1224\.  
Pattern: `arn:.*`   
Required: No

 **createdAt**   <a name="robomaker-Type-WorldExportJobSummary-createdAt"></a>
The time, in milliseconds since the epoch, when the world export job was created\.  
Type: Timestamp  
Required: No

 **status**   <a name="robomaker-Type-WorldExportJobSummary-status"></a>
The status of the world export job\.    
Pending  
The world export job request is pending\.  
Running  
The world export job is running\.   
Completed  
The world export job completed\.   
Failed  
The world export job failed\. See `failureCode` for more information\.   
Canceled  
The world export job was cancelled\.  
Canceling  
The world export job is being cancelled\.
Type: String  
Valid Values:` Pending | Running | Completed | Failed | Canceling | Canceled`   
Required: No

 **worlds**   <a name="robomaker-Type-WorldExportJobSummary-worlds"></a>
A list of worlds\.  
Type: Array of strings  
Array Members: Minimum number of 1 item\. Maximum number of 100 items\.  
Length Constraints: Minimum length of 1\. Maximum length of 1224\.  
Pattern: `arn:.*`   
Required: No

## See Also<a name="API_WorldExportJobSummary_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/robomaker-2018-06-29/WorldExportJobSummary) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/robomaker-2018-06-29/WorldExportJobSummary) 
+  [AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/robomaker-2018-06-29/WorldExportJobSummary) 
+  [AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/robomaker-2018-06-29/WorldExportJobSummary) 