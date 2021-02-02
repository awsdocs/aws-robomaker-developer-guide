# Cancelling a World Generation Job<a name="worlds-managing-generation-jobs-cancel"></a>

You can cancel a world generation job that is in progress\.

**To cancel a world generation job**  
Follow the steps under one of the following tabs:

------
#### [ Using the console ]<a name="worlds-managing-generation-jobs-cancel-con"></a>

1. Sign in to the AWS RoboMaker console at [https://console\.aws\.amazon\.com/robomaker/](https://console.aws.amazon.com/robomaker/)\.

1. In the left navigation pane, choose **Simulation WorldForge**, and then choose **Generation jobs**\.

1. On the **Generation jobs** page, choose the world generation job you want to cancel\. 

1. Choose **Cancel**\. On the **Cancel generation job** page, choose **Cancel job** to cancel the job\. 

------
#### [ Using the AWS CLI ]<a name="worlds-managing-generation-jobs-cancel-api"></a>

**Example**  
The following AWS CLI example uses the `list-world-generation-jobs` to list existing world generation jobs, and then it uses `cancel-world-generation-job` to cancel a specific world generation job\.   

```
$ aws robomaker list-world-generation-jobs
$ aws robomaker cancel-world-generation-job --job my-world-generation-job-arn
```

------