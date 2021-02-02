# FinishedWorldsSummary<a name="API_FinishedWorldsSummary"></a>

Information about worlds that finished\.

## Contents<a name="API_FinishedWorldsSummary_Contents"></a>

 **failureSummary**   <a name="robomaker-Type-FinishedWorldsSummary-failureSummary"></a>
Information about worlds that failed\.  
Type: [FailureSummary](API_FailureSummary.md) object  
Required: No

 **finishedCount**   <a name="robomaker-Type-FinishedWorldsSummary-finishedCount"></a>
The total number of finished worlds\.  
Type: Integer  
Required: No

 **succeededWorlds**   <a name="robomaker-Type-FinishedWorldsSummary-succeededWorlds"></a>
A list of worlds that succeeded\.  
Type: Array of strings  
Array Members: Minimum number of 1 item\. Maximum number of 100 items\.  
Length Constraints: Minimum length of 1\. Maximum length of 1224\.  
Pattern: `arn:.*`   
Required: No

## See Also<a name="API_FinishedWorldsSummary_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/robomaker-2018-06-29/FinishedWorldsSummary) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/robomaker-2018-06-29/FinishedWorldsSummary) 
+  [AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/robomaker-2018-06-29/FinishedWorldsSummary) 
+  [AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/robomaker-2018-06-29/FinishedWorldsSummary) 