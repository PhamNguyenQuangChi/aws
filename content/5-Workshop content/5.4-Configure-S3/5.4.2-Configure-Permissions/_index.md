---
title : "Access Permission Configuration"
date : 2024-01-01
weight : 2
chapter : false
pre : " <b> 5.4.2. </b> "
---

In the **Dental Clinic Management System**, securing image data (such as personal photos of doctors and patients) is extremely important. Therefore, the system does not enable Public Access, but instead uses a dynamic access-granting mechanism through the Backend.

### 1. Bucket Security Policy

During the Bucket creation step, we kept the default setting of **Block all public access**.

This means that no one on the Internet can view or directly download images from Amazon S3 using the original URL. If someone attempts to access it directly, Amazon S3 will block the request and return an **Access Denied** error.

Only the Backend application (through the IAM User `dental-backend-user` with `AmazonS3FullAccess` permission) can properly communicate with, read from, and write files to this Bucket.

### 2. Granting Display Access via Pre-signed URL

For the Frontend (ReactJS) to be able to display images to users, the Spring Boot Backend acts as an intermediary that grants access through the **Pre-signed URL** mechanism (a URL with a digital signature for authentication).

In the Backend source code, the `AwsConfig` class initializes the `S3Presigner` Bean:

```java
    @Bean
    public S3Presigner s3Presigner(AwsCredentialsProvider credentialsProvider) {
        return S3Presigner.builder()
                .region(Region.of(region))
                .credentialsProvider(credentialsProvider)
                .build();
    }
```

This `S3Presigner` object is responsible for generating temporary, signed URLs that grant time-limited access to specific objects in the Bucket. When the Frontend requests to view an image, the Backend uses this Bean to generate a Pre-signed URL and returns it to the client, allowing the browser to load the image directly from S3 without exposing the Bucket to public access.