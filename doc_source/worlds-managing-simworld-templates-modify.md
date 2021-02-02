# Modifying a Simulation World Template<a name="worlds-managing-simworld-templates-modify"></a>

Select the floor plan to customize the number and types of rooms and the connections between rooms in the floor plan\. Choose interiors to customize flooring, walls, and furniture\.

**To modify a simulation world template**  
Follow the steps on one of the following tabs:

------
#### [ Using the console ]<a name="worlds-managing-simworld-templates-update-con"></a>

**To modify the simulation world template**

1. Sign in to the AWS RoboMaker console at [https://console\.aws\.amazon\.com/robomaker/](https://console.aws.amazon.com/robomaker/)\.

1. On the AWS RoboMaker console, expand **Simulation WorldForge** in the left navigation pane and then select **World templates**\.

1. On the **World templates** page, choose the simulation world template you want to modify\.

1. Choose **Edit** or **Override** next to each element you want to modify\. For more information about simulation world template components, see [Understanding Simulation World Templates](worlds-managing-simworld-templates-components.md)\. 

------
#### [ Using the AWS CLI ]<a name="worlds-managing-simworld-templates-update-api"></a>

**Example**  
The following AWS CLI example uses `list-world-templates` to list existing templates, and then it uses `describe-world-template` to view the details of a simulation world template and `get-world-template-body` to retrieve the template body JSON and write it to a file\.   

```
$ aws robomaker list-world-templates
$ aws robomaker describe-world-template --template my-simulation-world-template-arn
$ aws robomaker get-world-template-body --template my-simulation-world-template-arn --output json > myTemplateBody.json
$ aws robomaker update-world-template-body --template my-simulation-world-template-arn --template-body file://myTemplateBody.json
```

------