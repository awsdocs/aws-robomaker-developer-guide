# Configuring Custom Uploads<a name="simulation-job-custom-upload-configuration"></a>

When you want to capture output files and other artifacts from your simulation job, you can configure custom uploads\. You can configure custom uploads for your robot application and your simulation application\. When you configure a custom upload, files you specify are uploaded from the simulation job to the Amazon S3 simulation output location you provide\. This can be useful when you want to review or analyze application output generated during a simulation run or reuse artifacts\. 

Before you can configure custom uploads, you must provide an Amazon S3 output destination for your simulation job\. AWS RoboMaker will upload matching files to a folder using a name you specify\. Matching files can be uploaded when all of the simulation job tools terminate or uploaded as they are produced and then removed\. 

Default upload configurations are automatically added to your custom upload configurations unless you turn them off\. The default upload configuration uploads ROS and Gazebo default logging output\. This maintains compatibility with past simulation job output configurations\. which uploaded ROS and Gazebo default logging output\. You can turn off the default upload configuration when you configure a simulation job in the console\. You can also turn it off by setting `useDefaultUploadConfigurations` to `false` in the API [https://docs.aws.amazon.com/robomaker/latest/dg/API_CreateSimulationJob.html](https://docs.aws.amazon.com/robomaker/latest/dg/API_CreateSimulationJob.html)\. 

Your simulation applications are extraded onto a single 128gb partition\. You have write access to the partition\. 

## Adding a Custom Upload Configuration<a name="simulation-job-custom-upload-configuration-add"></a>

To create a custom upload configuration, you need to specify a prefix that specifies where the files will be uploaded to in Amazon S3, a Unix glob path specifying the files to upload, and an upload behavior specifying when the files are uploaded\. 

### Name<a name="simulation-job-custom-upload-configuration-add-name"></a>

A prefix that specifies how files will be uploaded in Amazon S3\. It is appended to the simulation output location to determine the final path\. 

 For example, if your simulation output location is `s3://my-bucket` and your upload configuration name is `robot-test`, your files will be uploaded to `s3://my-bucket/<simid>/<runid>/robot-test`\. 

### Path<a name="simulation-job-custom-upload-configuration-add-path"></a>

The path specifies which files are uploaded\. Standard Unix glob matching rules are accepted subject to the following: 
+ The path must begin with `/home/robomaker/` or `/var/log`\. 
+ The path must not contain a reverse path expression \(`/..`\)\. 
+ Symbolic links are not followed\.
+ You can use `**` as a *super asterisk* in your path\. For example, specifying `/var/log/**.log` causes all `.log` files in the `/var/log` directory tree to be collected\. 

  You can also use the standard asterisk as a standard wildcard\. For example, `/var/log/system.log*` matches files such as `system.log_1111`, `system.log_2222`, and so on in `/var/log`\. 

### Upload Behavior<a name="simulation-job-custom-upload-configuration-add-upload"></a>

You can select one of the following upload behaviors:
+ **Upload on terminate** \(`UPLOAD_ON_TERMINATE`\) uploads all files matching the path once the simulation job enters the terminating state\. AWS RoboMaker will attempt to upload logs for a maximum of 60 minutes\. 

  AWS RoboMaker does not begin uploading files until all of your tools running in the simulation have stopped\.
+ **Upload rolling with auto remove** \(`UPLOAD_ROLLING_AUTO_REMOVE`\) uploads all files matching the path as they are generated\. Paths are checked every 5 seconds\. When the files are uploaded, the source files are deleted\. Once a file is deleted, if a new file is generated with the same name, it will replace the previously uploaded file\. AWS RoboMaker performs a final check for files once all of your applications running in the simulation have stopped\. 

  Upload rolling with auto remove is useful for uploading rolling logs\. Write or stream output to an "active" file which is not covered by the path glob\. Once you're done writing to the active file, roll the file into a location covered by the path glob to be uploaded and removed\. 

  This setting can help you conserve space in your simulation job\. It can also help you access files before your simulation job terminates\. 

The simulation job partition size is 128gb\. If your simulation job ends for any reason, AWS RoboMaker will try to upload all files specified in your custom upload configuration\. 

For more information about information captured from a running simulation job, see [Accessing Simulation Job Data](simulation-job-data.md)\. 