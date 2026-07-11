---
title : "Create S3 Bucket"
date : 2024-01-01
weight : 1
chapter : false
pre : " <b> 5.4.1. </b> "
---

In this step, we will create an **Amazon S3 Bucket** to store images for the **Dental Clinic Management System**.

### Create the S3 Bucket

1. Log in to the **AWS Management Console**.
2. Search for **Amazon S3**.
3. Select **Buckets**.
4. Select **Create bucket**.
5. Configure the Bucket with the following information:
   - **Bucket name:** `dental-service-images-huy`
   - **AWS Region:** `Asia Pacific (Singapore) - ap-southeast-1`
6. Keep the default settings and select **Create bucket**.

Once created successfully, the Bucket will appear in the list of Buckets in Amazon S3.

![Amazon S3 Bucket](/images/5-Workshop/5.1-Workshop-overview/S3.png)

### Verify the Bucket

Select the **dental-service-images-huy** Bucket to check its stored objects.

Inside the Bucket, the system has organized folders to manage images by function:

- **avatars/**: Stores profile pictures.
- **clinics/**: Stores clinic images.
- **services/**: Stores service images.

![Amazon S3 Objects](/images/5-Workshop/5.1-Workshop-overview/s3-objects.png)

### Verify CloudFront

Once created successfully, the Distribution's status will change to **Enabled**.

Copy the CloudFront **Domain name** to use in the Backend or Frontend when accessing images.

![CloudFront Running](/images/5-Workshop/5.1-Workshop-overview/cloufront.png)

After completing this step, the system will use CloudFront to distribute images from Amazon S3, helping to increase loading speed and improve access performance.

Once this step is complete, Amazon S3 is ready for the Backend to store and retrieve the system's images.