---
title : "Deploying the Backend on EC2"
date : 2024-01-01
weight : 6
chapter : false
pre : " <b> 5.6. </b> "
---

In this section, we will deploy the **Spring Boot Backend** of the **Dental Clinic Management System** to **Amazon EC2**. Once successfully deployed, the Backend will connect to AWS services such as **Amazon DynamoDB**, **Amazon S3**, **Amazon SES**, and **Amazon SNS** to provide the system's full set of features.

---

### 5.6.1. Create an EC2 Instance

Log in to the **AWS Management Console**, search for **Amazon EC2**, and select **Launch Instance**.

Configure the EC2 instance as follows:

- **Name:** Dental-Backend
- **Amazon Machine Image (AMI):** Amazon Linux 2023
- **Instance type:** t3.micro
- **Key pair:** Use an existing key pair or create a new one to connect via SSH.
- **Security Group:**
  - SSH (22)
  - HTTP (80)
  - Custom TCP (8080)

Once the configuration is complete, click **Launch Instance** to create the server.

![Create EC2](/aws/images/5-Workshop/5.1-Workshop-overview/EC2p3.png)

---

### 5.6.2. Connect to EC2

Once the EC2 instance status changes to **Running**, use **EC2 Instance Connect** or SSH to connect to the server.

Example:

```bash
ssh -i keydental.pem ec2-user@<Public-IP>
```

Once connected successfully, update the system and install Docker to prepare for application deployment.

---

### 5.6.3. Deploy the Backend

Upload the Backend's source code or Docker image to EC2.

Next, start the application using Docker:

```bash
docker build -t dental-backend .
docker run -d -p 8080:8080 --env-file .env dental-backend
```

Once the application starts successfully, the Backend will automatically connect to:

- Amazon DynamoDB
- Amazon S3
- Amazon SES
- Amazon SNS

to handle data storage, image management, and email notifications.

---

### 5.6.4. Verify the System

Once deployment is complete, access the Backend via the EC2 instance's Public IP:

```text
http://<Public-IP>:8080
```

Alternatively, use **Postman** to test the system's APIs.

If the Backend responds successfully, can access data from Amazon DynamoDB, upload images to Amazon S3, and send emails via Amazon SES and Amazon SNS, then the deployment process is complete.