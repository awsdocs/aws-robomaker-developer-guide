# Step 4: Use the Generated World in the Hello World Simulation<a name="worlds-creating-getting-started-using-world"></a>

In this section, you create a simulation job that runs the Hello World application with the new world you generated\. 

**To use the generated world in the Hello World simulation**

1. Sign in to the AWS RoboMaker console at [https://console\.aws\.amazon\.com/robomaker/](https://console.aws.amazon.com/robomaker/)\.

1. On the AWS RoboMaker console, expand **Simulations** on the left and then choose **Simulation jobs**\.

1. On the **Simulation jobs** page, choose the Hello World simulation job\. It is the simulation job with a robot application named **AWSRoboMakerHelloWorld**\. 

1. On the **Simulation jobs detail** page, choose **Actions** and then choose **Clone**\. 

1. On the **Review and create simulation job** page, next to **Step 3: Specify simulation application**, choose **Edit**\. 

1. On the **Specify simulation application** page, change **Launch file** to `worldforge_world.launch`\. 

1. On the **Specify simulation application** page, expand **Import world from WorldForge**, and then choose **Browse worlds**\. 

1. On the **Choose worlds** page, under **World**, choose the world you previously created, and then choose **Choose world**\. 

1. On the **Specify simulation application** page, choose **Next**\. 

1. On the **Review and create simulation job** page, choose **Create**\. 

1. You can explore the simulation using simulation tools\. For more information about simulation tools, see [Simulation Tools](simulation-tools.md)\. For other ways to explore the simulation, see [Explore the Simulation](gs-simulation.md#gs-simulation-explore)\. 