---
title : "Configure Amazon S3"
date : 2024-01-01
weight : 4
chapter : false
pre : " <b> 5.4. </b> "
---

In the **Dental Clinic Management System**, **Amazon S3 (Simple Storage Service)** is used to store the system's image files, such as doctor photos, service images, and files uploaded by users.

### 1. Creating an S3 Bucket

Log in to the **AWS Management Console**, search for **Amazon S3**, and select **Buckets**.

On the Amazon S3 interface, select **Create bucket** to create a new Bucket.

Set up the basic information:

- **Bucket name:** `dental-service-images-huy`
- **AWS Region:** `Asia Pacific (Singapore) - ap-southeast-1`

After completing the configuration, select **Create bucket**.

![Amazon S3 Bucket](/images/5-Workshop/5.1-Workshop-overview/S3.png)

Once created successfully, the `dental-service-images-huy` Bucket will appear in the Buckets list and is ready for use.

---

### 2. Configuring Amazon S3 in the Backend

After creating the Bucket, configure the Bucket information in the Backend's `application.yml` file.

```yaml
aws:
  region: ${AWS_REGION}

  s3:
    bucket-name: ${AWS_S3_BUCKET_NAME}
```

Where:

- `AWS_REGION`: The AWS region where the service is deployed.
- `AWS_S3_BUCKET_NAME`: The Amazon S3 Bucket name (`dental-service-images-huy`).

The Backend will use this information to connect to Amazon S3 and perform upload, download, and image management operations for the system.

After completing the configuration and starting the application, the Backend can store and retrieve images directly from Amazon S3.