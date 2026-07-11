---
title : "Create EC2 Instance"
date : 2024-01-01
weight : 1
chapter : false
pre : " <b> 5.6.1. </b> "
---

---
title : "Create EC2 Instance"
date : 2024-01-01
weight : 1
chapter : false
pre : " <b> 5.6.1. </b> "
---

In this step, we will create an **Amazon EC2 Instance** to deploy the Spring Boot Backend of the **Dental Clinic Management System**.

### Access Amazon EC2

Log in to the **AWS Management Console**, search for **EC2**, and select the **EC2** service.

In the left-hand menu, select **Instances**, then click **Launch instances** to begin creating a new server.

### Configure the Instance Name

In the **Name and tags** section, enter the instance name:

```text
Dental-Backend
```

This name makes it easy to identify the server used for deploying the system's Backend.

### Select the Operating System

In the **Application and OS Images (Amazon Machine Image)** section, select:

```text
Amazon Linux 2023 AMI
```

This AMI provides a stable Linux environment for installing Docker and running the Backend application.

### Select the Instance Type

In the **Instance type** section, select:

```text
t3.micro
```

This instance type is suitable for a hands-on practice and test deployment environment.

### Select the Key Pair

In the **Key pair (login)** section, select the previously created Key Pair:

```text
keydental
```

This Key Pair is used to connect via SSH to the EC2 Instance once the server has been launched.

![EC2 Configuration](/images/5-Workshop/5.1-Workshop-overview/EC2p1.png)

### Configure the Security Group

In the **Network settings** section, create a new Security Group or use an existing one.

In this workshop, the Security Group is configured to open the necessary ports:

| Type | Port | Purpose |
|------|------|----------|
| SSH | 22 | SSH connection to EC2 |
| HTTP | 80 | Access the application via HTTP |
| Custom TCP | 8080 | Access the Spring Boot Backend |

The Source is configured as:

```text
0.0.0.0/0
```

to allow access from the Internet in this hands-on environment.

![EC2 Security Group](/images/5-Workshop/5.1-Workshop-overview/EC2p2.png)

### Launch the EC2 Instance

Once the configuration is complete, review the **Summary** panel on the right side of the screen.

If all the information is correct, click **Launch instance** to create the EC2 Instance.

Once successfully launched, AWS will display the message **Successfully initiated launch of instance**.

### Verify the Instance

Go back to the **Instances** page to check the status of the EC2 Instance.

Once the Instance status changes to **Running** and the **Status check** shows success, the EC2 instance is ready to use.

![EC2 Running](/images/5-Workshop/5.1-Workshop-overview/EC2p3.png)

Once this step is complete, we have successfully created the EC2 Instance used to deploy the system's Spring Boot Backend.