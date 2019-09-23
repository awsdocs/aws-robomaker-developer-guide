# Environment variables created by AWS RoboMaker<a name="simulation-job-envvars"></a>

AWS RoboMaker defines the following simulation job environment variables:
+ AWS\_ROBOMAKER\_SIMULATION\_JOB\_ID
+ AWS\_ROBOMAKER\_SIMULATION\_JOB\_ARN
+ AWS\_ROBOMAKER\_SIMULATION\_RUN\_ID

You can access these variables from your application or from the command\-line\. For example, to get the current simulation job ARN in Python, use `os.environ.get("AWS_ROBOMAKER_SIMULATION_JOB_ARN")`\. 

If you specified an Amazon Simple Storage Service output bucket for the simulation job, you can use the environment variables to find the output path\. AWS RoboMaker writes output to `s3://bucketname/AWS_ROBOMAKER_SIMULATION_JOB_ID/AWS_ROBOMAKER_SIMULATION_RUN_ID`\. You can use this to manage objects in Amazon S3 from code or the command\-line\. 