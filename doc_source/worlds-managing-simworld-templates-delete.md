# Deleting a Simulation World Template<a name="worlds-managing-simworld-templates-delete"></a>

When you no longer need a simulation world template, you can delete it\.

------
#### [ Using the console ]<a name="worlds-managing-simworld-templates-delete-con"></a>

1. Sign in to the AWS RoboMaker console at [https://console\.aws\.amazon\.com/robomaker/](https://console.aws.amazon.com/robomaker/)\.

1. In the left navigation pane, choose **Simulation WorldForge**, and then choose **World templates**\.

1. Choose the **Id** of a simulation world template, choose **Template actions**, choose **Delete**, and then confirm the deletion by selecting **Delete** in the dialog box\. 

------
#### [ Using the AWS CLI ]<a name="worlds-managing-simworld-templates-delete-api"></a>

**Example**  
The following AWS CLI example uses `list-world-templates` to list existing templates, and then it uses `delete-world-template` to delete a simulation world template\.   

```
$ aws robomaker list-world-templates
$ aws robomaker delete-world-template --template my-simulation-world-template-arn
```

------