---
title : "Connect Backend"
date : 2024-01-01
weight : 2
chapter : false
pre : " <b> 5.3.2. </b> "
---

In this section, we'll look at how the Spring Boot Backend is configured to securely connect to the **Amazon DynamoDB** service through the AWS SDK for Java.

### 1. Credentials Configuration

For the Backend to have access to DynamoDB, the system needs to be provided with authentication credentials (Access Key & Secret Key). Instead of hardcoding these values directly into the code, the project uses the `application.yml` file to read these values from **Environment Variables**:

```yaml
aws:
  credentials:
    access-key-id: ${AWS_ACCESS_KEY_ID}
    secret-access-key: ${AWS_SECRET_ACCESS_KEY}
  region: ${AWS_REGION}
```

### 2. Verifying the DynamoDB Connection

After configuring the connection credentials, run the Spring Boot Backend with the following command:

```bash
mvn spring-boot:run
```

When the application starts up, the `DynamoDbTableInitializer` class will automatically check the DynamoDB tables. If a table already exists, the system will display a `Table already exists` message.

```text
Checking and creating DynamoDB tables if they do not exist...
Table already exists: users
Table already exists: invoices
Table already exists: feedbacks
Table already exists: doctor_schedules
Table already exists: doctors
Table already exists: services
Table already exists: consultations
Table already exists: blogs
Table already exists: appointments
Table already exists: categories
Table already exists: specialties
Table already exists: clinics
```

The Terminal output shows that the Backend has successfully connected to Amazon DynamoDB:

![DynamoDB Tables](/aws/images/5-Workshop/5.1-Workshop-overview/connetdb.png)

The logs above confirm that the Backend was able to access DynamoDB and successfully verify the system's data tables.