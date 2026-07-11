---
title : "Cleaning Up Resources"
date : 2024-01-01
weight : 8
chapter : false
pre : " <b> 5.8. </b> "
---

After completing the Workshop and successfully verifying that the system works, the final step is to clean up the resources created on AWS in order to avoid unnecessary costs.

In this section, we will go through and delete the resources used during the deployment of the **Dental Clinic Management System**.

### 5.8.1. Delete the EC2 Instance

1. Access **Amazon EC2**.
2. Select **Instances**.
3. Select the EC2 Instance that was created.
4. Select **Instance state → Terminate instance**.
5. Confirm the deletion.

![Terminate EC2](/images/5-Workshop/5.1-Workshop-overview/xoaEC2.png)

---

### 5.8.2. Delete the Amazon S3 Bucket

1. Access **Amazon S3**.
2. Select the project's Bucket.
3. Delete all objects within the Bucket.
4. Then select **Delete bucket**.
5. Enter the Bucket name to confirm and complete the deletion.

> **Note:** In this Workshop, the team **did not delete the Amazon S3 Bucket**, as it is still being used to store the system's images and to support the development and testing process in subsequent phases.

---

### 5.8.3. Delete the Amazon DynamoDB Tables

1. Access **Amazon DynamoDB**.
2. Select **Tables**.
3. Select the project's tables, such as:
   - users
   - doctors
   - services
   - appointments
   - invoices
   - feedbacks
   - consultations
   - clinics
4. Select **Delete table**.
5. Enter the confirmation and complete the deletion.

> **Note:** In this Workshop, the team **did not delete the Amazon DynamoDB tables**, as the data is still being used for the system's development, testing, and demo processes.

### 5.8.5. Delete the Amazon SES Identity

1. Access **Amazon SES**.
2. Select **Configuration → Identities**.
3. Select the verified Email Identity.
4. Select **Delete** to remove the Identity.

> **Note:** In this Workshop, the team **did not delete the Email Identity on Amazon SES**, as it is still being used to send appointment confirmation emails and other notifications from the system.

### 5.8.5. Delete the Amazon SES Identity

1. Access **Amazon SES**.
2. Select **Configuration → Identities**.
3. Select the verified Email Identity.
4. Select **Delete** to remove the Identity.

> **Note:** In this Workshop, the team **did not delete the Email Identity on Amazon SES**, as it is still being used to send appointment confirmation emails and other notifications from the system.

After completing the steps above, all resources used in the Workshop have been cleaned up. This helps avoid unnecessary costs and keeps the AWS account tidy and ready for future deployments.