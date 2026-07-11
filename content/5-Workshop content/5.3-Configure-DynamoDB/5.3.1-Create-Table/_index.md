---
title : "Create DynamoDB Table"
date : 2024-01-01
weight : 1
chapter : false
pre : " <b> 5.3.1. </b> "
---
## Automatic DynamoDB Table Initialization

In the **Dental Clinic Management System**, **Amazon DynamoDB** tables are not created manually through the AWS Console. Instead, they are automatically initialized through the Spring Boot Backend source code.

The Backend uses the `DynamoDbTableInitializer` class to check for and create the required tables when the application starts up.

```java
@Configuration
public class DynamoDbTableInitializer {

    private final DynamoDbEnhancedClient enhancedClient;

    public DynamoDbTableInitializer(DynamoDbEnhancedClient enhancedClient) {
        this.enhancedClient = enhancedClient;
    }

    @PostConstruct
    public void createTables() {
        createTableIfNotExists("users", User.class);
        createTableIfNotExists("invoices", Invoice.class);
        createTableIfNotExists("feedbacks", Feedback.class);
        createTableIfNotExists("doctor_schedules", DoctorSchedule.class);
        createTableIfNotExists("doctors", Doctor.class);
        createTableIfNotExists("services", DentalService.class);
        createTableIfNotExists("consultations", Consultation.class);
        createTableIfNotExists("blogs", Blog.class);
        createTableIfNotExists("appointments", Appointment.class);
        createTableIfNotExists("categories", Category.class);
        createTableIfNotExists("specialties", Specialty.class);
        createTableIfNotExists("clinics", Clinic.class);
    }
}
```

When the Spring Boot Backend runs, the `@PostConstruct` annotation automatically triggers the `createTables()` method. This method checks for and creates the DynamoDB tables if they don't already exist.

The tables that are automatically created include:

| Table | Purpose |
|-------|---------|
| users | Stores user account information |
| invoices | Stores invoice information |
| feedbacks | Stores patient reviews and feedback |
| doctor_schedules | Stores doctors' work schedules |
| doctors | Stores doctor information |
| services | Stores dental service information |
| consultations | Stores consultation requests |
| blogs | Stores blog posts |
| appointments | Stores appointment bookings |
| categories | Stores blog post categories |
| specialties | Stores medical specialties |
| clinics | Stores clinic information |

After the application starts successfully, go to **AWS Console → DynamoDB → Tables** to verify that the tables have been created.

![DynamoDB Tables](/aws/images/5-Workshop/5.1-Workshop-overview/dynamodb-tables.png)

If the tables show an **Active** status, the DynamoDB table initialization process is complete.
