# AWS CloudFormation Practice Project

This repository contains a collection of AWS CloudFormation YAML templates and supporting files for learning and practicing infrastructure-as-code concepts on AWS. The templates demonstrate how to provision core AWS resources such as networking components, compute instances, load balancers, auto scaling, IAM, S3 storage, and a simple RDS database.

## Project Overview

The project is organized as a set of hands-on CloudFormation examples that can be used to:

- Build a VPC with public and private subnets
- Create EC2-based web infrastructure and load balancing resources
- Configure Auto Scaling with CloudWatch alarms
- Provision IAM users, groups, roles, and policies
- Host a static website from Amazon S3
- Create a basic Amazon RDS database instance

## Repository Contents

- [vpc-template.yaml](vpc-template.yaml) – Creates a VPC, subnets, internet gateway, route table, security groups, load balancer, and sample EC2 web servers.
- [ec2.yaml](ec2.yaml) – Contains a basic RDS CloudFormation example (DB instance definition).
- [rds.yaml](rds.yaml) – Creates a simple MySQL RDS database instance.
- [asg.yaml](asg.yaml) – Demonstrates an Auto Scaling Group, launch template, and scaling policy.
- [iam.yaml](iam.yaml) – Defines an IAM user, developer group, role, and an attached policy.
- [s3-bucket-template.yaml](s3-bucket-template.yaml) – Creates an S3 bucket template.
- [s3-static.yaml](s3-static.yaml) – Creates an S3 static website bucket with public read access.
- [aws-cli-commands.txt](aws-cli-commands.txt) – Helpful AWS CLI commands for creating, describing, and deleting CloudFormation stacks.
- [index.html](index.html) – Sample static website content used for the S3-hosted website example.

## Prerequisites

Before using the templates, make sure you have:

- An AWS account
- AWS CLI installed and configured
- Appropriate IAM permissions to create CloudFormation stacks and related AWS resources
- A valid key pair if you plan to use EC2 instances that require SSH access

## How to Deploy a Template

You can create a CloudFormation stack from any template using the AWS CLI:

```bash
aws cloudformation create-stack \
  --stack-name <stack-name> \
  --template-body file://<template-file>.yaml \
  --profile <profile-name>
```

To check the status of a stack:

```bash
aws cloudformation describe-stacks --stack-name <stack-name> --profile <profile-name>
```

To delete a stack when you are done:

```bash
aws cloudformation delete-stack --stack-name <stack-name>
```

## Notes

- These templates are intended for learning and practice. Some values such as AMI IDs, bucket names, CIDR blocks, and IAM policy settings are hard-coded and should be adjusted for your environment.
- Some templates may need to be customized before deploying to production or to match your AWS account region and available resources.
- For EC2 access, be sure to use the correct SSH key and security group configuration.

## Learning Goal

This repository is a practical example of using AWS CloudFormation to automate infrastructure deployment and reinforce cloud engineering concepts in a repeatable, version-controlled way.
