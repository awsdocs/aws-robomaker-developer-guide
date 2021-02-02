# Creating a World Generation Job<a name="worlds-managing-generation-jobs-create"></a>

Create a world generation job to generate worlds with different room and interior configurations\. Each world generation job can generate up to 50 worlds\. 

**To create a world generation job**  
Follow the steps on one of the following tabs:

------
#### [ Using the console ]<a name="worlds-managing-generation-jobs-create-con"></a>

**To create a simulation world template**

1. Sign in to the AWS RoboMaker console at [https://console\.aws\.amazon\.com/robomaker/](https://console.aws.amazon.com/robomaker/)\.

1. On the AWS RoboMaker console, expand **Simulation WorldForge** on the left and then choose **World templates**\.

1. On the **World templates** page, choose the simulation world template you want to use to generate worlds, and then choose **Generate worlds**\. 

1. On the **Generate worlds** page, specify the **Number of floor plans**\. The number of floor plans multiplied by the number of interior variations per floor plan must not exceed 50\. 

1. Specify the number of **Interior variations per floor plan**\. The number of floor plans multiplied by the number of interior variations per floor plan must not exceed 50\. 

1. *Optional:* Add **World tags** that will be assigned to all of the worlds you generate\. 

1. *Optional:* Add **Generation job tags** that will be assigned to the generation job\. These tags will not apply to worlds you generate\. 

1. Choose **Generate**\. 

   You can track the progress of your world generation job in the **World generation detail** page\. The time required to generate your worlds depends on the complexity of the simulation world template and the number of worlds you are generating\. 

------
#### [ Using the AWS CLI ]<a name="worlds-managing-generation-jobs-create-api"></a>

**Example**  
You can generate worlds from a simulation world template using the AWS CLI\. Use `create-world-generation-job` to create the world generation job\.   
The following AWS CLI example shows how to generate 4 worlds with 2 floor plans with 2 different interior floor plans\.   

```
$ aws robomaker list-world-templates
$ aws robomaker create-world-generation-job --template my-simulation-world-template-arn --worldCount floorplanCount=2,interiorCountPerFloorplan=2
$ aws robomaker list-world-generation-jobs
$ aws robomaker describe-world-generation-job --job my-world-generation-job-arn
```

------