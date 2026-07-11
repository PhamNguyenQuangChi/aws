---
title : "Kết nối Backend"
date : 2024-01-01
weight : 2
chapter : false
pre : " <b> 5.3.2. </b> "
---

Trong phần này, chúng ta sẽ xem xét cách Backend Spring Boot cấu hình để kết nối một cách an toàn với dịch vụ **Amazon DynamoDB** thông qua AWS SDK for Java.

### 1. Cấu hình thông tin xác thực (Credentials)

Để Backend có quyền truy cập vào DynamoDB, hệ thống cần được cung cấp thông tin xác thực (Access Key & Secret Key). Thay vì hardcode (gắn cứng) trực tiếp trong code, dự án sử dụng file `application.yml` để đọc các giá trị này từ **Biến môi trường (Environment Variables)**:

```yaml
aws:
  credentials:
    access-key-id: ${AWS_ACCESS_KEY_ID}
    secret-access-key: ${AWS_SECRET_ACCESS_KEY}
  region: ${AWS_REGION}

### 2. Kiểm tra kết nối DynamoDB

Sau khi cấu hình thông tin kết nối, chạy Backend Spring Boot bằng lệnh:

```bash
mvn spring-boot:run
```

Khi ứng dụng khởi động, class `DynamoDbTableInitializer` sẽ tự động kiểm tra các bảng DynamoDB. Nếu bảng đã tồn tại, hệ thống sẽ hiển thị thông báo `Table already exists`.


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
Kết quả trong Terminal cho thấy Backend đã kết nối thành công với Amazon DynamoDB:

![DynamoDB Tables](/images/5-Workshop/5.1-Workshop-overview/connetdb.png)
Các log trên chứng minh Backend đã truy cập được DynamoDB và kiểm tra thành công các bảng dữ liệu của hệ thống.