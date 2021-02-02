# Viewing a World Export Job<a name="worlds-managing-export-jobs-view"></a>

View the status and other details of a world export job\.

**To see the details of a world export job**  
Follow the steps on one of the following tabs:

------
#### [ Using the console ]<a name="worlds-managing-export-jobs-view-con"></a>

1. Sign in to the AWS RoboMaker console at [https://console\.aws\.amazon\.com/robomaker/](https://console.aws.amazon.com/robomaker/)\.

1. In the left navigation pane, choose **Simulation WorldForge**, and then choose **Export jobs**\.

1. Choose the **ID** of a world export job to view its details\. You can also search and cancel world export jobs\. 

------
#### [ Using the AWS CLI ]<a name="worlds-managing-export-jobs-view-api"></a>

**Example**  
The following AWS CLI example uses the `list-world-export-jobs` to list existing world export jobs, and then it uses `describe-world-export-job` to view the details of a specific world export job\.   

```
$ aws robomaker list-world-export-jobs
$ aws robomaker describe-world-export-job --job my-world-export-job-arn
```

------