# Monitoring AWS RoboMaker with Amazon CloudWatch<a name="monitoring-aws-robomaker-cloudwatch"></a>

AWS RoboMaker sends metrics to Amazon CloudWatch\. You can use the AWS Management Console, the AWS CLI, or an API to list the metrics that AWS RoboMaker sends to CloudWatch\. 

Metrics exist only in the region in which they are created\. Metrics cannot be deleted, but they automatically expire after 15 months if no new data is published to them\. 

For more information about Amazon CloudWatch, see the [Amazon CloudWatch User Guide](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/)\. 

**Topics**
+ [AWS RoboMaker Simulation Metrics](#monitoring-aws-robomaker-metrics)
+ [AWS RoboMaker Usage Metrics](#monitoring-aws-robomaker-metrics)

## AWS RoboMaker Simulation Metrics<a name="monitoring-aws-robomaker-metrics"></a>

You can monitor AWS RoboMaker simulation jobs using Amazon CloudWatch, which collects information from your simulation job and creates readable, near real\-time metrics\. Information is provided at 1\-minute frequency\. 

The following metrics are available in the `SimulationJobId` dimension\.


| Metric | Description | 
| --- | --- | 
| `RealTimeFactor`  | The ratio of the amount of time that was simulated versus wall clock time\. For example, if it takes an hour to simulate 30 minutes, the factor is \.5\. More complex simulations have a lower real time factor\.   | 
| `vCPU*` | Number of virtual CPU cores used by the simulation job Unit: Count  | 
| `Memory*` | Amount of Memory, in GB, used by the SimulationJob  Unit: GB  | 
| `SimulationUnit*` | SimulationUnit is calculated based on vCPU and memory consumption of the Simulation Job Unit: Count  | 

**Important**  
Metrics marked with \* are for estimation purposes\. AWS RoboMaker emits metrics while preparing to run a simulation job\. Charges do not accrue until the simulation job is in the `Running` state\. 

## AWS RoboMaker Usage Metrics<a name="monitoring-aws-robomaker-metrics"></a>

You can use CloudWatch usage metrics to provide visibility into your account's usage of resources\. Use these metrics to visualize your current service usage on CloudWatch graphs and dashboards\. 

AWS RoboMaker usage metrics correspond to AWS service quotas\. You can configure alarms that alert you when your usage approaches a service quota\. For more information about CloudWatch integration with service quotas, see [Service Quotas Integration and Usage Metrics](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/CloudWatch-Service-Quota-Integration.html)\. 

The following metrics are available in the `AWS/Usage` dimension\.


| Metric | Description | 
| --- | --- | 
| `ResourceCount`  |  The number of the specified resources running in your account\. The resources are defined by the dimensions associated with the metric\. The most useful statistic for this metric is `MAXIMUM`, which represents the maximum number of resources used during the 1\-minute period\.  | 

The following dimensions are used to refine the usage metrics that are published by AWS RoboMaker\.


| Dimension | Description | 
| --- | --- | 
| `Service`  | The name of the AWS service containing the resource\. For AWS RoboMaker usage metrics, the value for this dimension is `RoboMaker`\.  | 
| `Type` | The type of entity that is being reported\. Currently, the only valid value for AWS RoboMaker usage metrics is `Resource`\.  | 
| `Resource` |  The type of resource that is running\. Currently, the valid values for AWS RoboMaker usage metrics are `RobotApplication`, `SimulationApplication`, `ActiveSimulationJob` and `ActiveSimulationJobBatch`\.   | 
| `Class` | The class of resource being tracked\. For AWS RoboMaker usage metrics with `ActiveSimulationJob` as the value of the Resource dimension, the valid value is `CPU`\. The value for this dimension define the kind of compute resources used by the SimulationJobs reported by that metric\. For others the class value is `None`\.  | 

These metrics are emitted every minute\. Use these metrics to monitor usage and then request a corresponding limit increase if needed\. For more information about monitoring your usage, see [Visualizing Your Service Quotas and Setting Alarms](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/CloudWatch-Quotas-Visualize-Alarms.html)\.