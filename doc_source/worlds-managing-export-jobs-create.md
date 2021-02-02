# Creating a World Export Job<a name="worlds-managing-export-jobs-create"></a>

You can select worlds to export to your Amazon S3 bucket\. All worlds selected for the export will be in a single \.zip file\. 

**To create a world export job**  
Follow the steps on one of the following tabs:

------
#### [ Using the console ]<a name="worlds-managing-export-jobs-create-con"></a>

You can export one world per export job\. 

**To create a simulation world template**

1. Sign in to the AWS RoboMaker console at [https://console\.aws\.amazon\.com/robomaker/](https://console.aws.amazon.com/robomaker/)\.

1. On the AWS RoboMaker console, expand **Simulation WorldForge** in the left navigation pane, and then choose **Worlds**\.

1. On the **Worlds** page, choose **Create export job**\. 

1. On the **Create export job** page, choose a **World** to export\. 

1. Choose an **IAM role** with `PutObject`, `GetObject` and `AbortMultipartUpload` permissions to your Amazon S3 bucket\. Choose **Create** to have a role with appropriate permissions created for you\. 

1. Choose an **S3 destination for worlds output**\. You can also create a new Amazon S3 bucket by choosing **Create new S3 bucket** near the bottom of the page\. 

1. *Optional:* On the **Create export job** page, add tags that will be assigned to the exported world\. 

1. Choose **Create** to create the world export job\.

   You can track its progress of the export job in the world export job details page\. You are taken there automatically after you create the job\. 

------
#### [ Using the AWS CLI ]<a name="worlds-managing-export-jobs-create-api"></a>

**Example**  
You can export worlds using the AWS CLI\. Use `create-world-export-job` to create the world export job\. You can export one world per export job\.   
The following AWS CLI example shows how to export a world\. First, you can list worlds using `list-worlds`, and then call `create-world-export-job` specifying a world arn\. You can check status by calling `list-world-export-jobs` and `describe-world-export-job`\.   

```
$ aws robomaker list-worlds
$ aws robomaker create-world-export-job --worlds my-simulation-world-arn --iam-role my-iam-role-arn --outputLocation s3Bucket=my-bucket,s3prefix=prefix
$ aws robomaker list-world-export-jobs
$ aws robomaker describe-world-export-job --job my-world-export-job-arn
```

------