---
title : "Introduction"
date : 2024-01-01
weight : 1
chapter : false
pre : " <b> 5.1. </b> "
---

#### System Introduction

The **Dental Clinic Management System** is a cloud-based web application designed to streamline dental clinic operations and provide patients with a convenient online appointment booking experience. The system enables patients to register, log in, browse available dental services, view dentist information, schedule appointments, and track appointment status. In addition, administrators can efficiently manage dentists, services, patients, and appointments through a centralized management portal.

The application is developed using a **3-Tier Architecture**, separating the Presentation Layer (Frontend), Application Layer (Backend), and Data Layer (Database). This architecture improves scalability, maintainability, security, and overall system performance while making it easier to manage and expand future functionalities.

#### Workshop Overview

This workshop demonstrates how to deploy the **Dental Clinic Management System** on **Amazon Web Services (AWS)** using multiple AWS services to build a secure, scalable, and highly available cloud-native application.

The workshop covers the deployment and configuration of the following AWS services:

- **AWS Amplify** is used to host and deploy the ReactJS frontend application.
- **Amazon CloudFront** delivers static content globally with low latency, while **Amazon Route 53** manages DNS and domain routing.
- **AWS WAF** protects the application from common web attacks such as SQL Injection (SQLi) and Cross-Site Scripting (XSS).
- **Amazon EC2** hosts the Spring Boot backend application and processes business logic through RESTful APIs.
- **Application Load Balancer (ALB)** distributes incoming traffic to improve application availability and scalability.
- **Amazon DynamoDB** stores application data, including user accounts, dentists, services, and appointment information.
- **Amazon S3** stores static assets, uploaded images, and supporting documents.
- **AWS Identity and Access Management (IAM)** manages authentication and authorization for AWS resources.
- **AWS Secrets Manager** securely stores sensitive credentials and application secrets.
- **AWS Key Management Service (AWS KMS)** encrypts sensitive data and manages encryption keys.
- **Amazon CloudWatch** monitors system performance, collects logs, and provides operational insights.
- **Amazon SNS** delivers system notifications, while **Amazon SES** sends appointment confirmation and notification emails to users.

By following this workshop, readers will learn how to prepare the AWS environment, deploy both frontend and backend applications, configure database and storage services, implement security best practices, monitor system performance, and perform resource cleanup after deployment.

![AWS Architecture](/aws/images/5-Workshop/5.1-Workshop-overview/drawio.png)
/**
 * SYSTEM WORKFLOW
 *
 * 1. User/Doctor accesses the website via a domain name managed by Amazon Route 53.
 *
 * 2. Amazon Route 53 routes the request to Amazon CloudFront to optimize
 *    access speed and content delivery.
 *
 * 3. AWS WAF inspects and filters requests before they reach CloudFront,
 *    protecting against attacks such as SQL Injection, Cross-Site Scripting (XSS),
 *    and other abnormal/malicious requests.
 *
 * 4. Amazon CloudFront distributes the ReactJS frontend deployed on AWS Amplify,
 *    along with static assets stored in Amazon S3.
 *
 * 5. When the user performs actions such as login, appointment booking, or
 *    data management, the Frontend (AWS Amplify) sends API requests to the
 *    Application Load Balancer (ALB).
 *
 * 6. The Application Load Balancer (ALB) forwards these requests to the
 *    Amazon EC2 instance(s) running the Spring Boot backend application.
 *
 * 7. Amazon EC2 handles the core business logic of the system, including
 *    user authentication, doctor management, service management,
 *    appointment scheduling, and other functions.
 *
 * 8. During processing, Amazon EC2 stores and retrieves images from Amazon S3,
 *    and uses Amazon SES and Amazon SNS to send emails and notifications
 *    when needed.
 *
 * 9. Finally, Amazon EC2 reads from and writes to Amazon DynamoDB.
 *    Meanwhile, Amazon CloudWatch monitors system activity and sends alerts
 *    via Amazon SNS when it detects issues or metrics exceeding configured
 *    thresholds.
 */