# Creating Worlds with Simulation WorldForge<a name="worlds-creating"></a>

Simulation WorldForge makes it easier and faster to create simulation worlds\. Worlds are generated from the simulation world templates you define\. The simulation world template specifies the world layout, room dimensions, furnishings, how rooms are connected, and other details\. Walls and floors and other room features can have material properties\. Rooms can be furnished by room type automatically or you can select potential furnishings\. Generated worlds can be used in your simulation jobs and exported to use on your developer machine\. 

Simulation WorldForge can help you manage simulation workloads that require a large number of simulation worlds with domain randomization\. Common Simulation WorldForge scenarios include the following:
+ **Regression testing** — Test your robotics applications in hundreds of worlds to verify correct behavior\. 
+ **Synthetic imagery data generation ** — You can capture images from the generated worlds to use in other robotic applications\. For example, you can capture images of rooms with different furniture layout and material composition\.
+ **Reinforcement learning** — Create hundreds of unique worlds with an interior structure for your robotic application to explore\. You control the composition of the world\. 
+ **Developing algorithms** — A robotics navigation engineer could verify a navigation algorithm succeeds in a known layout with different furniture placement\. A robotics localization engineer can ensure a layout algorithm detects different structural elements in different floor plans\. 

You do not need to know world generation algorithms or how to create and manage infrastructure\. Simulation WorldForge and AWS RoboMaker are fully managed services\. 