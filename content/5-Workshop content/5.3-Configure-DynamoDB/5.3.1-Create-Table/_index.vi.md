---
title : "Tạo bảng DynamoDB"
date : 2024-01-01
weight : 1
chapter : false
pre : " <b> 5.3.1. </b> "
---

Trong hệ thống **Dental Clinic Management System**, các bảng **Amazon DynamoDB** không được tạo thủ công trên AWS Console mà được tự động khởi tạo thông qua mã nguồn Backend Spring Boot.

Backend sử dụng class `DynamoDbTableInitializer` để kiểm tra và tạo các bảng cần thiết khi ứng dụng được khởi động.

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

Khi Backend Spring Boot chạy, annotation `@PostConstruct` sẽ tự động gọi phương thức `createTables()`. Phương thức này kiểm tra và tạo các bảng DynamoDB nếu chúng chưa tồn tại.

Các bảng được tạo tự động gồm:

| Table | Chức năng |
|-------|-----------|
| users | Lưu thông tin tài khoản người dùng |
| invoices | Lưu thông tin hóa đơn |
| feedbacks | Lưu đánh giá của bệnh nhân |
| doctor_schedules | Lưu lịch làm việc của bác sĩ |
| doctors | Lưu thông tin bác sĩ |
| services | Lưu thông tin dịch vụ nha khoa |
| consultations | Lưu yêu cầu tư vấn |
| blogs | Lưu bài viết |
| appointments | Lưu lịch hẹn khám |
| categories | Lưu danh mục bài viết |
| specialties | Lưu chuyên khoa |
| clinics | Lưu thông tin phòng khám |

Sau khi ứng dụng khởi động thành công, truy cập **AWS Console → DynamoDB → Tables** để kiểm tra các bảng đã được tạo.

![DynamoDB Tables](/images/5-Workshop/5.1-Workshop-overview/dynamodb-tables.png)

Nếu các bảng hiển thị trạng thái **Active**, quá trình khởi tạo bảng DynamoDB đã hoàn tất.