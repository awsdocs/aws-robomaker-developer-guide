# Step 3: Generate a Simulation World from the Simulation World Template<a name="worlds-creating-getting-started-world-gen"></a>

In this section, you create a world generation job using the simulation world template you created\. A world generation job generates the worlds using the specified template parameters\. When you create the generation job, you specify the number of floor plans and interior variations per floor plan in the worlds\. 

**To create a simulation world from a simulation world template**

1. Sign in to the AWS RoboMaker console at [https://console\.aws\.amazon\.com/robomaker/](https://console.aws.amazon.com/robomaker/)\.

1. On the AWS RoboMaker console, expand **Simulation WorldForge** on the left and then choose **World templates**\.

1. On the **World templates** page, choose the sample template you created, and then choose **Generate worlds**\.

1. On the **Generate worlds** page, specify `1` for **Number of floor plans** and **Interior variations per floor plan**\. Simulation WorldForge generates 1 world, or the `number of floor plans * interior variations per floor plan`\. You can generate up to 50 worlds\. 

1. Choose **Generate** to begin world generation\.

1. On the **World generation job details** page, you can track world generation progress\. Generated worlds appear under **Completed worlds**\. 