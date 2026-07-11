---
title: "Workshop"
date: 2024-01-01
weight: 5
chapter: false
pre: " <b> 5. </b> "
---

# Deploying the Dental Clinic Management Website on AWS

#### Overview

In this workshop, I will demonstrate the deployment process of the **Dental Clinic Management Website** on the **Amazon Web Services (AWS)** cloud platform.

The project is designed to **address the limitations of traditional dental clinic management**, including:

- Managing appointments manually using paper or spreadsheets, which can easily lead to scheduling conflicts and data loss.
- Requiring patients to call or visit the clinic directly to book appointments, resulting in inconvenience for both patients and clinic staff.
- Difficulty in managing dentists, services, appointments, and patient information within a centralized system.
- Limited capability to monitor system performance and application health as the number of users increases.
- Challenges in scaling and maintaining applications deployed on traditional on-premises infrastructure.

To overcome these challenges, the system is built using a **3-Tier Architecture**, with **ReactJS** as the Frontend, **Spring Boot** as the Backend, and **Amazon DynamoDB** as the NoSQL database. Deploying the application on AWS provides improved scalability, high availability, enhanced security, and simplified infrastructure management.

Throughout this workshop, readers will learn how to deploy the application step by step on AWS, including preparing the cloud environment, deploying the Frontend and Backend, configuring database and storage services, implementing security features, monitoring system performance, testing the application, and cleaning up AWS resources after deployment.

The AWS services used in this workshop include:

- Amazon EC2
- AWS Amplify
- Amazon DynamoDB
- Amazon S3
- Amazon CloudFront
- Amazon Route 53
- AWS WAF
- AWS Secrets Manager
- AWS Key Management Service (KMS)
- Amazon CloudWatch
- Amazon SNS
- Amazon SES
- AWS Identity and Access Management (IAM)

#### Contents

1. [Introduction](5.1-Workshop-overview/)
2. [Prerequisites](5.2-Prerequiste/)
3. [Configure DynamoDB](5.3-Configure-DynamoDB/)
4. [Configure Amazon S3](5.4-Configure-S3/)
5. [Configure Amazon SES & SNS](5.5-Configure-SES/)
6. [Deploy Backend on EC2](5.6-Deploy-EC2/)
7. [System Testing](5.7-System-Testing/)
8. [Resource Cleanup](5.8-Cleanup/)