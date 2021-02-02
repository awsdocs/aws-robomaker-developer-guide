# Deleting a Generated World<a name="worlds-managing-generated-worlds-delete"></a>

When you no longer need a world, you can delete it\.

------
#### [ Using the console ]<a name="worlds-managing-generated-worlds-delete-con"></a>

1. Sign in to the AWS RoboMaker console at [https://console\.aws\.amazon\.com/robomaker/](https://console.aws.amazon.com/robomaker/)\.

1. In the left navigation pane, choose **Simulation WorldForge**, and then choose **Worlds**\.

1. Choose the worlds you want to delete\. You can use the preview thumbnails to find worlds\. You can also search by tags, IDs, or templates\. 

1. Choose **Delete**, and then choose **Delete** on the **Delete world** page\. 

------
#### [ Using the AWS CLI ]<a name="worlds-managing-generated-worlds-delete-api"></a>

**Example**  
The following AWS CLI example uses `list-worlds` to list existing worlds, and then it uses `batch-delete-worlds` to delete two worlds\.   

```
$ aws robomaker list-worlds
$ aws robomaker batch-delete-worlds --worlds my-world-arn1,my-world-arn2
```

------