# WorldCount<a name="API_WorldCount"></a>

The number of worlds that will be created\. You can configure the number of unique floorplans and the number of unique interiors for each floor plan\. For example, if you want 1 world with 20 unique interiors, you set `floorplanCount = 1` and `interiorCountPerFloorplan = 20`\. This will result in 20 worlds \(`floorplanCount` \* `interiorCountPerFloorplan)`\. 

If you set `floorplanCount = 4` and `interiorCountPerFloorplan = 5`, there will be 20 worlds with 5 unique floor plans\. 

## Contents<a name="API_WorldCount_Contents"></a>

 **floorplanCount**   <a name="robomaker-Type-WorldCount-floorplanCount"></a>
The number of unique floorplans\.  
Type: Integer  
Required: No

 **interiorCountPerFloorplan**   <a name="robomaker-Type-WorldCount-interiorCountPerFloorplan"></a>
The number of unique interiors per floorplan\.  
Type: Integer  
Required: No

## See Also<a name="API_WorldCount_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/robomaker-2018-06-29/WorldCount) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/robomaker-2018-06-29/WorldCount) 
+  [AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/robomaker-2018-06-29/WorldCount) 
+  [AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/robomaker-2018-06-29/WorldCount) 