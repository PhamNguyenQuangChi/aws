---
title : "Prerequisites"
date : 2024-01-01
weight : 2
chapter : false
pre : " <b> 5.2. </b> "
---

In this section, we will prepare the required AWS resources for deploying the **Dental Clinic Management System**.

#### Prepare an AWS Account

Sign in to the **AWS Management Console** and select the **Asia Pacific (Singapore) - ap-southeast-1** Region to ensure that all resources are deployed in the same Region.

#### Prepare an IAM User

Create or use an IAM User named **dental-backend-user** and attach the following AWS Managed Policies:

- AmazonEC2FullAccess
- AmazonDynamoDBFullAccess
- AmazonS3FullAccess
- AmazonSESFullAccess
- CloudWatchFullAccess

![create stack](/aws/images/5-Workshop/5.2-Prerequisite/IAM.png)

These permissions allow the IAM User to deploy and manage the AWS services required by the system.

#### Prepare AWS Resources

Before deploying the application, ensure that the following AWS services are available:

- Amazon EC2 for deploying the Spring Boot backend.
- Amazon DynamoDB for storing application data.
- Amazon S3 for storing images and files.
- Amazon SES for sending appointment confirmation emails.
- Amazon CloudWatch for monitoring and logging system activities.

#### Verify the Environment

After completing the preparation steps, verify that the IAM User has the required permissions and that all AWS services are ready before proceeding with the deployment in the following sections.