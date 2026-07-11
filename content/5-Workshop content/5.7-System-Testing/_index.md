---
title : "System Testing"
date : 2024-01-01
weight : 7
chapter : false
pre : " <b> 5.7. </b> "
---

After completing the deployment of the **Dental Clinic Management System** on AWS, the final step is to test the entire system to ensure that all services are running stably and can communicate with one another.

In this section, we will verify that the Backend on Amazon EC2 has successfully connected to Amazon DynamoDB, Amazon S3, Amazon SES, and Amazon SNS, and check the system's core functionalities.

### 5.7.1. Check EC2 Status

First, access the **Amazon EC2 Console** and check the status of the Instance.

If the Instance shows a **Running** status and passes all **Status Checks**, this indicates that the server is ready to run the Backend application.

![EC2 Running](/aws/images/5-Workshop/5.1-Workshop-overview/EC2p3.png)

---

### 5.7.2. Verify Data Storage

Log in to the system and create or update some data.

Then access **Amazon DynamoDB** to confirm that the data has been successfully saved to the system's tables.

![DynamoDB](/aws/images/5-Workshop/5.1-Workshop-overview/database.png)

---

### 5.7.3. Verify Image Upload

Upload an avatar or service image from the system's interface.

Once the upload is successful, access **Amazon S3** and check the Bucket to confirm that the image file has been stored.

![Amazon S3](/aws/images/5-Workshop/5.1-Workshop-overview/s3avata.png)

---

### 5.7.4. Verify Email Sending

Proceed to book an appointment or trigger the email-sending feature from the system.

If the user receives a notification email in their Gmail inbox, this confirms that Amazon SES has been configured and is working correctly.

![Amazon SES](/aws/images/5-Workshop/5.1-Workshop-overview/nhangmail.png)

---

After completing the above testing steps, the **Dental Clinic Management System** has been successfully deployed on the AWS platform. The Backend runs stably on Amazon EC2 and can connect to Amazon DynamoDB, Amazon S3, Amazon SES, and Amazon SNS to fully support the system's functionalities.