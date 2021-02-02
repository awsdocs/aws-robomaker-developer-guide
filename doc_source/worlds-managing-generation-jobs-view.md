# Viewing a World Generation Job<a name="worlds-managing-generation-jobs-view"></a>

You can view world generation progress, summary information, and other details about a world generation job\. 

**To see the details of a world generation job**  
Follow the steps on one of the following tabs:

------
#### [ Using the console ]<a name="worlds-managing-generation-jobs-view-con"></a>

1. Sign in to the AWS RoboMaker console at [https://console\.aws\.amazon\.com/robomaker/](https://console.aws.amazon.com/robomaker/)\.

1. In the left navigation pane, choose **Simulation WorldForge**, then choose **World templates**\.

1. Choose the **Id** of a world generation job to view its details\. You can find generation jobs using the search bar\. 

------
#### [ Using the AWS CLI ]<a name="worlds-managing-generation-jobs-view-api"></a>

**Example**  
The following AWS CLI example uses the `list-world-generation-jobs` to list existing world generation jobs, and then it uses `describe-world-generation-job` to view the details of a specific world generation job\.   

```
$ aws robomaker list-world-generation-jobs
$ aws robomaker describe-world-generation-job --job my-world-generation-job-arn
```

------