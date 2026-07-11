---
title: "Proposal"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

# Dental Clinic Management System
## Dental Clinic Appointment and Management Website on AWS Cloud

### 1. Executive Summary

The **Dental Clinic System** is a web-based application that enables patients to book dental appointments online, browse available services, track appointment status, and receive notifications from the clinic. The system also assists dentists and administrators in managing appointments, dental services, patient records, and daily clinic operations.

The system is built on a **Cloud Native Architecture** using AWS services to provide high availability, security, scalability, and performance. The frontend is deployed using **AWS Amplify**, while the backend is developed with **Spring Boot** and hosted on **Amazon EC2**. Application data is stored in **Amazon DynamoDB**, medical images and uploaded files are stored in **Amazon S3**, and services such as **CloudWatch, SNS, SES, AWS WAF, IAM, Secrets Manager, and AWS KMS** are integrated to ensure reliable and secure operation.

---

## 2. Problem Statement

### Current Problems

Many dental clinics still manage appointments manually through phone calls or paper-based records, which leads to several issues:

- Difficult appointment management.
- Appointment conflicts and scheduling errors.
- Inefficient patient information management.
- No automatic notification system.
- Limited scalability as the number of patients increases.

### Proposed Solution

The **Dental Clinic System** provides a cloud-based appointment management platform running on AWS Cloud.

Patients can:

- Register and log in.
- Book dental appointments.
- View appointment history.
- Cancel appointments.
- Browse available dental services.
- Track appointment status.

Dentists can:

- View their schedules.
- Manage patient appointments.
- Update treatment status.

Administrators can:

- Manage users.
- Manage dentists.
- Manage dental services.
- Manage appointments.
- Monitor overall system activities.

### Benefits

- Reduce appointment processing time.
- Automate appointment scheduling.
- Improve patient experience.
- Provide a scalable cloud infrastructure.
- Enhance data security.
- Reduce operational costs by utilizing AWS Cloud services.

---

## 3. Solution Architecture

The system follows a **Cloud Native Architecture** on AWS.

The frontend is deployed using **AWS Amplify**, together with **Amazon Route 53**, **Amazon CloudFront**, and **AWS WAF** to improve performance and protect the application.

The backend is deployed on **Amazon EC2** behind an **Application Load Balancer (ALB)** to handle incoming requests efficiently.

Application data is stored in **Amazon DynamoDB**, while images and uploaded files are stored in **Amazon S3**.

Sensitive configuration data is securely managed using **AWS Secrets Manager** and encrypted with **AWS KMS**.

**Amazon CloudWatch** monitors system resources, while **Amazon SNS** and **Amazon SES** deliver alerts and appointment confirmation emails.

![Dental Clinic Architecture](/aws/images/2-Proposal/Proposal.jpg)

### AWS Services Used

- **Amazon Route 53:** Manages domain names and routes users to the application using DNS.
- **Amazon CloudFront:** Delivers content globally with low latency through a Content Delivery Network (CDN).
- **AWS WAF:** Protects the application against common web attacks such as SQL Injection and Cross-Site Scripting (XSS).
- **AWS Amplify:** Hosts and deploys the React frontend with automatic build and deployment from GitHub.
- **Application Load Balancer (ALB):** Distributes incoming traffic across backend services to improve availability.
- **Amazon EC2:** Hosts the Spring Boot backend application and processes business logic.
- **Amazon DynamoDB:** Stores users, dentists, services, appointments, and other application data.
- **Amazon S3:** Stores doctor images, service images, user uploads, and static files.
- **AWS Secrets Manager:** Securely stores sensitive credentials such as JWT secrets and API keys.
- **AWS Key Management Service (KMS):** Encrypts sensitive data and manages encryption keys.
- **Amazon CloudWatch:** Collects logs and monitors application performance.
- **Amazon SNS:** Sends system notifications and operational alerts.
- **Amazon SES:** Sends appointment confirmations, reminders, and email notifications.
- **AWS Identity and Access Management (IAM):** Controls user permissions and access to AWS resources.

### Component Design

**Frontend**

- ReactJS
- AWS Amplify
- Amazon CloudFront
- Amazon Route 53
- AWS WAF

**Backend**

- Spring Boot
- Amazon EC2
- Application Load Balancer

**Database**

- Amazon DynamoDB

**Storage**

- Amazon S3

**Security**

- AWS IAM
- AWS Secrets Manager
- AWS KMS

**Monitoring**

- Amazon CloudWatch
- Amazon SNS
- Amazon SES

---

## 4. Technical Implementation

### Implementation Phases

The project is divided into four main phases, from requirement analysis to deployment on AWS Cloud.

1. **Requirement Analysis and System Design:** Analyze the requirements of the dental clinic, identify core features such as user management, dentist management, appointment scheduling, and service management, then design the database, user interface, and AWS Cloud architecture.

2. **System Development:** Develop the frontend using ReactJS and the backend using Java Spring Boot following the RESTful API architecture. Configure Amazon DynamoDB for data storage and Amazon S3 for image storage while implementing all business functionalities.

3. **AWS Deployment:** Deploy the frontend using AWS Amplify and the backend on Amazon EC2. Configure Application Load Balancer (ALB), Amazon Route 53, Amazon CloudFront, and AWS WAF to improve performance, availability, and security.

4. **Testing, Optimization, and Operation:** Perform functional testing, security testing, and performance testing. Monitor the system using Amazon CloudWatch, configure Amazon SNS and Amazon SES for notifications and email confirmations, and optimize both cost and system performance before production deployment.

### Technical Requirements

**Frontend**

- ReactJS with Tailwind CSS.
- Axios for REST API communication.
- AWS Amplify deployment.
- Amazon CloudFront for CDN.
- Amazon Route 53 for DNS management.
- AWS WAF for application protection.

**Backend**

- Java Spring Boot.
- RESTful API architecture.
- JWT Authentication.
- Amazon EC2 deployment.
- Application Load Balancer.
- AWS Secrets Manager.
- AWS KMS.

**Database and Storage**

- Amazon DynamoDB for application data.
- Amazon S3 for storing images and uploaded files.

**Monitoring and Notification**

- Amazon CloudWatch for monitoring logs and resources.
- Amazon SNS for operational notifications.
- Amazon SES for appointment confirmation and reminder emails.

**Security**

- AWS IAM for access control.
- AWS Secrets Manager for credential management.
- AWS KMS for data encryption.

**Deployment Environment**

- Frontend: ReactJS + AWS Amplify.
- Backend: Java Spring Boot on Amazon EC2.
- Database: Amazon DynamoDB.
- Storage: Amazon S3.
- Domain: Amazon Route 53.
- CDN: Amazon CloudFront.
- Security: AWS WAF, IAM, Secrets Manager, AWS KMS.
- Monitoring: Amazon CloudWatch.
- Notification: Amazon SNS and Amazon SES.

---

## 5. Project Timeline

### Month 1

- Requirement analysis.
- UI/UX design.
- Database design.
- AWS architecture design.

### Month 2

- Backend development.
- Frontend development.
- DynamoDB integration.
- Amazon S3 integration.

### Month 3

- AWS deployment.
- System testing.
- Performance optimization.
- Final documentation.

---

## 6. Budget Estimation

Infrastructure costs are estimated using the **AWS Pricing Calculator**.

### Infrastructure Cost

- Amazon EC2: 0.30 USD/month
- Application Load Balancer: 0.06 USD/month
- Amazon DynamoDB: 0.08 USD/month
- Amazon S3: 0.10 USD/month
- AWS Amplify: 0.15 USD/month
- Amazon CloudFront: 0.05 USD/month
- Amazon Route 53: 0.04 USD/month
- AWS WAF: 0.10 USD/month
- Amazon CloudWatch: 0.05 USD/month
- Amazon SNS: 0.02 USD/month
- Amazon SES: 0.04 USD/month
- AWS Secrets Manager: 0.03 USD/month
- AWS KMS: 0.02 USD/month

**Total:** **1.04 USD/month**, approximately **12.48 USD/year** (estimated for a small-scale demonstration environment using AWS Free Tier whenever applicable).

---

## 7. Risk Assessment

### Risk Matrix

- Amazon EC2 failure.
- Unexpected traffic spikes.
- Internet connectivity issues.
- AWS configuration errors.
- Credential leakage.

### Mitigation Strategy

- Monitor the system with Amazon CloudWatch.
- Protect the application using AWS WAF.
- Store sensitive credentials in AWS Secrets Manager.
- Apply IAM role-based access control.
- Perform regular data backups.

### Contingency Plan

- Restore uploaded files from Amazon S3.
- Redeploy the backend on Amazon EC2.
- Analyze logs through Amazon CloudWatch.
- Notify administrators via Amazon SNS and Amazon SES.

---

## 8. Expected Outcomes

- Successfully develop an online dental appointment management system.
- Deploy a stable and secure application on AWS Cloud.
- Improve appointment management efficiency.
- Enhance patient experience.
- Provide a scalable cloud architecture for future expansion.
- Support future features such as online payment, AI chatbot, and Electronic Medical Records (EMR).
