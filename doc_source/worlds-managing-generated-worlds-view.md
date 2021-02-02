# Viewing a Generated World<a name="worlds-managing-generated-worlds-view"></a>

You can view the world status, the id of the simulation world template used to generate the world, and other details\. You can view images of the world in the console\. 

**To see the details of a world generation job**  
Follow the steps on one of the following tabs:

------
#### [ Using the console ]<a name="worlds-managing-generation-jobs-view-con"></a>

To view images of worlds in the console, you should have permissions to call ` DescribeWorldForgeImageRedirect` in the AWS RoboMaker API\. For more information, see [ Permissions Required to View Worlds in the AWS RoboMaker in the Console](auth-and-access-control.md#auth_access_required-permissions-view-worlds)\. 

1. Sign in to the AWS RoboMaker console at [https://console\.aws\.amazon\.com/robomaker/](https://console.aws.amazon.com/robomaker/)\.

1. In the left navigation pane, choose **Simulation WorldForge**, and then choose **Worlds**\.

1. Choose the **Id** of a world to view its details\. You can use the preview thumbnails to find worlds\. You can also search by tags, IDs, or templates\. 

1. On the **World details** page, you can review details including a larger preview image\. You can also export or delete the world\. 

------
#### [ Using the AWS CLI ]<a name="worlds-managing-generation-jobs-view-api"></a>

**Example**  
The following AWS CLI example uses `list-worlds` to list existing worlds, and then it uses `describe-world` to view the details of a specific world\.   

```
$ aws robomaker list-worlds
$ aws robomaker describe-world --world my-world-arn
```

------