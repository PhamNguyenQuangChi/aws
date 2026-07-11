---
title : "Configure Amazon DynamoDB"
date : 2024-01-01
weight : 3
chapter : false
pre : " <b> 5.3. </b> "
---

In this step, we will verify the **Amazon DynamoDB** tables used in the **Dental Clinic Management System**.

Sign in to the **AWS Management Console**, search for **DynamoDB**, and select **Tables**.

At this stage, all required database tables have been created and are ready for use.

The main tables used by the system are listed below:

| Table | Description |
|-------|-------------|
| users | Stores user account information |
| doctors | Stores dentist information |
| specialties | Stores dental specialties |
| services | Stores dental service information |
| appointments | Stores appointment records |
| doctor_schedules | Stores dentists' working schedules |
| consultations | Stores consultation requests |
| invoices | Stores invoice information |
| feedbacks | Stores patient feedback |
| blogs | Stores blog posts |
| categories | Stores blog categories |
| clinics | Stores clinic information |

![DynamoDB Tables](/aws/images/5-Workshop/5.1-Workshop-overview/dynamodb-tables.png)

Verify that all tables are in the **Active** state before proceeding with the next deployment steps.