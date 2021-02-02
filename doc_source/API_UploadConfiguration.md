# UploadConfiguration<a name="API_UploadConfiguration"></a>

Provides upload configuration information\. Files are uploaded from the simulation job to a location you specify\. 

## Contents<a name="API_UploadConfiguration_Contents"></a>

 **name**   <a name="robomaker-Type-UploadConfiguration-name"></a>
A prefix that specifies where files will be uploaded in Amazon S3\. It is appended to the simulation output location to determine the final path\.   
 For example, if your simulation output location is `s3://my-bucket` and your upload configuration name is `robot-test`, your files will be uploaded to `s3://my-bucket/<simid>/<runid>/robot-test`\.   
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 255\.  
Pattern: `[a-zA-Z0-9_\-]*`   
Required: Yes

 **path**   <a name="robomaker-Type-UploadConfiguration-path"></a>
 Specifies the path of the file\(s\) to upload\. Standard Unix glob matching rules are accepted, with the addition of `**` as a *super asterisk*\. For example, specifying `/var/log/**.log` causes all \.log files in the `/var/log` directory tree to be collected\. For more examples, see [Glob Library](https://github.com/gobwas/glob)\.   
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 1024\.  
Pattern: `.*`   
Required: Yes

 **uploadBehavior**   <a name="robomaker-Type-UploadConfiguration-uploadBehavior"></a>
Specifies when to upload the files:    
UPLOAD\_ON\_TERMINATE  
Matching files are uploaded once the simulation enters the `TERMINATING` state\. Matching files are not uploaded until all of your code \(including tools\) have stopped\.   
If there is a problem uploading a file, the upload is retried\. If problems persist, no further upload attempts will be made\.  
UPLOAD\_ROLLING\_AUTO\_REMOVE  
Matching files are uploaded as they are created\. They are deleted after they are uploaded\. The specified path is checked every 5 seconds\. A final check is made when all of your code \(including tools\) have stopped\. 
Type: String  
Valid Values:` UPLOAD_ON_TERMINATE | UPLOAD_ROLLING_AUTO_REMOVE`   
Required: Yes

## See Also<a name="API_UploadConfiguration_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/robomaker-2018-06-29/UploadConfiguration) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/robomaker-2018-06-29/UploadConfiguration) 
+  [AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/robomaker-2018-06-29/UploadConfiguration) 
+  [AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/robomaker-2018-06-29/UploadConfiguration) 