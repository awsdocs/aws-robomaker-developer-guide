# Configuring a AWS RoboMaker Simulation Job to Access Resources in an Amazon VPC<a name="vpc"></a>

Typically, you create resources inside Amazon Virtual Private Cloud \(Amazon VPC\) so that they cannot be accessed over the public Internet\. These resources could be AWS service resources, such as Amazon Redshift data warehouses, Amazon ElastiCache clusters, or Amazon RDS instances\. They could also be your own services running on your own EC2 instances\. By default, resources within a VPC are not accessible from within a AWS RoboMaker simulation job\. 

AWS RoboMaker runs your simulation job securely within a VPC by default\. However, to enable your AWS RoboMaker simulation job to access resources inside your private VPC, you must provide additional VPC\-specific configuration information that includes VPC subnet IDs and security group IDs\. AWS RoboMaker uses this information to set up elastic network interfaces [\(ENIs\)](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_ElasticNetworkInterfaces.html) that enable your simulation job to connect securely to other resources within your private VPC\.

AWS RoboMaker does not support connecting to resources within Dedicated Tenancy VPCs\. For more information, see [Dedicated VPCs](https://docs.aws.amazon.com/vpc/latest/userguide/dedicated-instance.html)\.

## Configuring a AWS RoboMaker Simulation Job for Amazon VPC Access<a name="vpc-configuring"></a>

You add VPC information to your AWS RoboMaker simulation job configuration using the `VpcConfig` parameter at the time you create a AWS RoboMaker simulation job \(see [CreateSimulationJob](API_CreateSimulationJob.md)\)\. The following is a AWS CLI example:
+ The `create-simulation-job` CLI command specifies the `--vpc-config` parameter to provide VPC information at the time you create a AWS RoboMaker simulation job\. In this example, a public IP is assigned\.

  ```
  $ aws robomaker create-simulation-job \
  --output-location s3Bucket=my-bucket,s3Prefix=my-output-folder \
  --max-job-duration-in-seconds 3600 \
  --iam-role my-role-arn \
  --failure-behavior Continue \
  --robot-applications application='my-robot-application-arn,launchConfig={packageName="hello_world_robot",launchFile="rotate.launch"}' \
  --simulation-applications application='my-simulation-application-arn,launchConfig={packageName="hello_world_simulation",launchFile="empty_world.launch"}' \
  --vpc-config assignPublicIp=true,subnets=comma-separated-vpc-subnet-ids,securityGroups=comma-separated-security-group-ids
  ```

  When a AWS RoboMaker simulation job is configured to run within a VPC, it incurs an additional ENI start\-up penalty\. This means address resolution may be delayed when trying to connect to network resources\.

## Internet Access for Simulation Jobs<a name="vpc-internet"></a>

AWS RoboMaker uses the VPC information you provide to set up ENIs that allow your AWS RoboMaker simulation job to access VPC resources\. Each ENI is assigned a private IP address from the IP address range within the Subnets you specify, but is not assigned any public IP addresses by default\.

If your AWS RoboMaker simulation job requires Internet access \(for example, to access AWS services that do not have VPC endpoints\), you can configure a NAT instance inside your VPC or you can use the Amazon VPC NAT gateway, or you can request RoboMaker to assign a public IP\. For more information, see [NAT Gateways](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-nat-gateway.html) in the *Amazon VPC User Guide*\. You cannot use an Internet gateway attached to your VPC, since that requires the ENI to have public IP addresses\. 

To configure internet access when using public Subnets, set `assignPublicIp=true` to assign a public IP to your ENI\.