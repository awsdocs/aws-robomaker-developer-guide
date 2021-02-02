# Configuring Permissions<a name="sample-applications-permissions"></a>

When you launch a sample program in the AWS RoboMaker console, you can provide an IAM role to use\. This section describes what you need to launch the samples\. 

For more information about AWS Identity and Access Management roles, see [Creating a Role to Delegate Permissions to an AWS Service](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_create_for-service.html)\.

## Minimum permissions<a name="sample-applications-permissions-many"></a>

To launch a sample application, you need a role that has:
+ A trust relationship with `robomaker.amazonaws.com`\.
+ A trust relationship with `lambda.amazonaws.com`\.
+ Sample application permissions\.

Use the following permissions to launch `Hello world` and `Robot monitoring`\.

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