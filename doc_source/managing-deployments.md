# Managing Deployments<a name="managing-deployments"></a>

In AWS RoboMaker, a robot application is delivered and installed onto a fleet of physical robots using deployment job\. The robot application must be build for the architecture supported by the physical robot \(for example, ARMHF\)\. 

You can set fleet and robot deployment timeouts\. The default fleet timeout is 30 days\. The default robot deployment timeout is 5 hours\. For example, if you have 100 robots in your fleet and you deploy to them sequentially with a robot timeout of 7 days, the deployment might take 700 days\. AWS RoboMaker will timeout the deployment at 30 days, the default fleet timeout\. 

**Topics**
+ [Conditional Deployment](conditional-deployment.md)
+ [Creating a deployment job](create-deployment-job.md)
+ [Viewing a Deployment Job](describe-deployment-job.md)