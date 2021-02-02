# Viewing a Simulation World Template<a name="worlds-managing-simworld-templates-view"></a>

View details about a simulation world template\.

**To see the details of a simulation world template**  
Follow the steps on one of the following tabs:

------
#### [ Using the console ]<a name="worlds-managing-simworld-templates-view-con"></a>

1. Sign in to the AWS RoboMaker console at [https://console\.aws\.amazon\.com/robomaker/](https://console.aws.amazon.com/robomaker/)\.

1. In the left navigation pane, choose **Simulation WorldForge**, and then choose **World templates**\.

1. Choose the **Id** of a simulation world template to view its details including its floor plan and interiors\. You can also generate worlds from the detail view\. 

------
#### [ Using the AWS CLI ]<a name="worlds-managing-simworld-templates-view-api"></a>

**Example**  
The following AWS CLI example uses `list-world-templates` to list existing templates, and then it uses `describe-world-template` and `get-world-template-body` to view the details of a simulation world template\.   

```
$ aws robomaker list-world-templates
$ aws robomaker describe-world-template --template my-simulation-world-template-arn
$ aws robomaker get-world-template-body --template my-simulation-world-template-arn
```

------