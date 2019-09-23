# Configuring Permissions<a name="sample-applications-permissions"></a>

When you launch a sample application in the AWS RoboMaker console, you can choose to provide an IAM role that is used to launch the sample application\. The permissions required vary by sample application\. This section describes the permissions needed to launch each sample application\. 

For more information about creating an AWS Identity and Access Management role for a service, see [Creating a Role to Delegate Permissions to an AWS Service](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_create_for-service.html)\.

## Minimum permissions<a name="sample-applications-permissions-many"></a>

To launch a sample application, you need a role that has:
+ A trust relationship with `robomaker.amazonaws.com`\.
+ A trust relationship with `lambda.amazonaws.com`\.
+ Sample application permissions\.

Use the following permissions to launch the Hello world, Robot monitoring, Self\-driving, and the Object\-following sample applications\. Other sample applications require these permissions and a set of additional permissions\. 

Replace `account#` with your account number\.

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Action": [
                "s3:ListBucket",
                "s3:GetObject",
                "s3:PutObject"
            ],
            "Resource": [
                "*"
            ],
            "Effect": "Allow"
        },
        {
            "Action": [
                "iam:PassRole"
            ],
            "Resource": "arn:aws:iam::account#:role/*",
            "Effect": "Allow"
        },
        {
            "Action": [
                "robomaker:*"
            ],
            "Resource": "*",
            "Effect": "Allow"
        },
        {
            "Action": [
                "ec2:AssociateRouteTable",
                "ec2:AttachInternetGateway",
                "ec2:CreateInternetGateway",
                "ec2:CreateSubnet",
                "ec2:CreateVpc",
                "ec2:CreateTags",
                "ec2:CreateRoute",
                "ec2:CreateRouteTable",
                "ec2:CreateSecurityGroup",
                "ec2:DeleteSubnet",
                "ec2:DescribeSecurityGroups",
                "ec2:DescribeSubnets",
                "ec2:DescribeVpcs"
            ],
            "Resource": "*",
            "Effect": "Allow"
        },
        {
            "Action": [
                "logs:CreateLogGroup",
                "logs:CreateLogStream",
                "logs:PutLogEvents"
            ],
            "Resource": [
                "arn:aws:logs:us-west-2:account#:log-group:/aws/lambda/*:*"
            ],
            "Effect": "Allow"
        },
        {
            "Condition": {
                "StringEquals": {
                    "iam:AWSServiceName": [
                        "robomaker.amazonaws.com"
                    ]
                }
            },
            "Action": "iam:CreateServiceLinkedRole",
            "Resource": "*",
            "Effect": "Allow"
        },
        {
            "Action": [
                "cloudformation:DescribeStacks"
            ],
            "Resource": "arn:aws:cloudformation:*:account#:stack/*",
            "Effect": "Allow"
        }
    ]
}
```

## Navigation<a name="sample-applications-permissions-nav"></a>

In addition to the minimum required permissions [minimum permissions](#sample-applications-permissions-many), the navigation sample application requires the additional permissions listed below\.

Replace `account#` with your account number\. 

```
{
    "Action": [
        "iam:PassRole"
    ],
    "Resource": "arn:aws:iam::account#:role/*",
    "Effect": "Allow"
},
{
    "Action": [
        "cloudformation:DescribeStacks"
    ],
    "Resource": "arn:aws:cloudformation:*:account#:stack/*",
    "Effect": "Allow"
},
{
    "Action": [
        "kinesis:DeleteStream",
        "kinesis:DescribeStream",
        "kinesis:CreateStream"
    ],
    "Resource": "arn:aws:kinesis:*:account#:stream/AmazonRekognitionPersonDetectionStream*",
    "Effect": "Allow"
},
{
    "Action": [
        "kinesisvideo:CreateStream"
    ],
    "Resource": "*",
    "Effect": "Allow"
},
{
    "Action": [
        "kinesisvideo:DescribeStream",
        "kinesisvideo:DeleteStream"
    ],
    "Resource": "arn:aws:kinesisvideo:*:account#:stream/RoboMakerPersonDetectionVideoStream*",
    "Effect": "Allow"
},
{
    "Action": [
        "rekognition:CreateCollection",
        "rekognition:DeleteCollection",
        "rekognition:IndexFaces"
    ],
    "Resource": "arn:aws:rekognition:*:account#:collection/roboMakerSampleAppPersonDetectionCollection*",
    "Effect": "Allow"
},
{
    "Action": [
        "rekognition:CreateStreamProcessor"
    ],
    "Resource": [
        "arn:aws:rekognition:*:account#:streamprocessor/personDetectionStreamProcessor*",
        "arn:aws:rekognition:*:account#:collection/roboMakerSampleAppPersonDetectionCollection*"
    ],
    "Effect": "Allow"
},
{
    "Action": [
        "rekognition:DeleteStreamProcessor",
        "rekognition:StartStreamProcessor",
        "rekognition:StopStreamProcessor"
    ],
    "Resource": "arn:aws:rekognition:*:account#:streamprocessor/personDetectionStreamProcessor*",
    "Effect": "Allow"
},
{
    "Action": [
        "s3:PutBucketNotification"
    ],
    "Resource": "*",
    "Effect": "Allow"
}
```

## Person detection<a name="sample-applications-permissions-detect"></a>

In addition to the minimum required permissions [minimum permissions](#sample-applications-permissions-many), the person detection sample application requires a trust relationship with `rekognition.amazonaws.com`\. You must also attach the policy `arn:aws:iam::aws:policy/service-role/AmazonRekognitionServiceRole` to the role\. 

It also requires the additional permissions listed below\. Replace `account#` with your account number\. 

```
{
    "Action": [
        "iam:PassRole"
    ],
    "Resource": "arn:aws:iam::account#:role/*",
    "Effect": "Allow"
},
{
    "Action": [
        "cloudformation:DescribeStacks"
    ],
    "Resource": "arn:aws:cloudformation:*:account#:stack/*",
    "Effect": "Allow"
},
{
    "Action": [
        "kinesis:DeleteStream",
        "kinesis:DescribeStream",
        "kinesis:CreateStream"
    ],
    "Resource": "arn:aws:kinesis:*:account#:stream/AmazonRekognitionPersonDetectionStream*",
    "Effect": "Allow"
},
{
    "Action": [
        "kinesisvideo:CreateStream"
    ],
    "Resource": "*",
    "Effect": "Allow"
},
{
    "Action": [
        "kinesisvideo:DescribeStream",
        "kinesisvideo:DeleteStream"
    ],
    "Resource": "arn:aws:kinesisvideo:*:account#:stream/RoboMakerPersonDetectionVideoStream*",
    "Effect": "Allow"
},
{
    "Action": [
        "rekognition:CreateCollection",
        "rekognition:DeleteCollection",
        "rekognition:IndexFaces"
    ],
    "Resource": "arn:aws:rekognition:*:account#:collection/roboMakerSampleAppPersonDetectionCollection*",
    "Effect": "Allow"
},
{
    "Action": [
        "rekognition:CreateStreamProcessor"
    ],
    "Resource": [
        "arn:aws:rekognition:*:account#:streamprocessor/personDetectionStreamProcessor*",
        "arn:aws:rekognition:*:account#:collection/roboMakerSampleAppPersonDetectionCollection*"
    ],
    "Effect": "Allow"
},
{
    "Action": [
        "rekognition:DeleteStreamProcessor",
        "rekognition:StartStreamProcessor",
        "rekognition:StopStreamProcessor"
    ],
    "Resource": "arn:aws:rekognition:*:account#:streamprocessor/personDetectionStreamProcessor*",
    "Effect": "Allow"
},
{
    "Action": [
        "s3:PutBucketNotification"
    ],
    "Resource": "*",
    "Effect": "Allow"
}
```

## Voice commands<a name="sample-applications-permissions-voice"></a>

In addition to the minimum required permissions [minimum permissions](#sample-applications-permissions-many), the voice command sample application requires the additional permissions listed below\.

Replace `account#` with your account number\. 

```
{
    "Action": [
        "lex:CreateBotVersion",
        "lex:GetBot",
        "lex:GetBotAlias",
        "lex:GetIntent",
        "lex:GetSlotType",
        "lex:PutBot",
        "lex:PutBotAlias",
        "lex:PutIntent",
        "lex:PutSlotType"
    ],
    "Resource": [
        "arn:aws:lex:*:account#:*"
    ],
    "Effect": "Allow"
},
{
    "Action": [
        "lex:GetImport",
        "lex:StartImport"
    ],
    "Resource": "*",
    "Effect": "Allow"
}
```