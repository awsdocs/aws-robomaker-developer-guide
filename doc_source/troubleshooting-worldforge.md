# Troubleshooting Simulation WorldForge<a name="troubleshooting-worldforge"></a>

This section can help you fix issues with Simulation WorldForge\.

**Topics**
+ [Why did my world generation job fail?](#troubleshooting-worldforge-worldgen)
+ [Why did my world export job fail?](#troubleshooting-worldforge-export)

## Why did my world generation job fail?<a name="troubleshooting-worldforge-worldgen"></a>

This section can help you fix issues with Simulation WorldForge simulation world generation\.

### Is your world count 0 or greater than 50?<a name="troubleshooting-worldforge-worldgen-count"></a>

If your world generation job did not complete, make sure your world count, `floorplanCount * interiorCountPerFloorplan`, is greater than 1 and less than 50\. 

## Why did my world export job fail?<a name="troubleshooting-worldforge-export"></a>

This section can help you fix issues with Simulation WorldForge world export jobs\.

### Do you have a trust policy for AWS RoboMaker?<a name="troubleshooting-worldforge-export-trust"></a>

If you are passing the full Amazon Resource Name \(ARN\) of the IAM role when you call `create-world-export-job` from the AWS CLI, your trust policy might have insufficient privileges\. Check the role to make sure it has a trust relationship with `robomaker.amazonaws.com`\. 

### Does your role have permissions to publish to Amazon S3?<a name="troubleshooting-worldforge-export-s3"></a>

If you specify an output Amazon S3 bucket for a export job, your role must have permissions to the bucket\. Update your trust policy to include the following permissions: 

```
{
  "Effect": "Allow",
  "Action": [
    "s3:AbortMultipartUpload",
    "s3:GetObject",
    "s3:PutObject"
  ],
  "Resource": “my-bucket"
}
```

### Did you modify or remove the bucket specified for the export job?<a name="troubleshooting-worldforge-export-modified"></a>

If you update your bucket during the export job, you may get a `ResourceNotFound` error from export job\. 