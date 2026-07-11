---
title : "Cấu hình Amazon S3"
date : 2024-01-01
weight : 4
chapter : false
pre : " <b> 5.4. </b> "
---

Trong **Dental Clinic Management System**, **Amazon S3 (Simple Storage Service)** được sử dụng để lưu trữ các tệp hình ảnh của hệ thống như ảnh bác sĩ, ảnh dịch vụ và các tệp được người dùng tải lên.

### 1. Tạo S3 Bucket

Đăng nhập vào **AWS Management Console**, tìm kiếm **Amazon S3** và chọn **Buckets**.

Tại giao diện Amazon S3, chọn **Create bucket** để tạo một Bucket mới.

Thiết lập các thông tin cơ bản:

- **Bucket name:** `dental-service-images-huy`
- **AWS Region:** `Asia Pacific (Singapore) - ap-southeast-1`

Sau khi hoàn tất cấu hình, chọn **Create bucket**.

![Amazon S3 Bucket](/aws/images/5-Workshop/5.1-Workshop-overview/S3.png)

Sau khi tạo thành công, Bucket `dental-service-images-huy` sẽ xuất hiện trong danh sách Buckets và sẵn sàng để sử dụng.

---

### 2. Cấu hình Amazon S3 trong Backend

Sau khi tạo Bucket, cấu hình thông tin Bucket trong file `application.yml` của Backend.

```yaml
aws:
  region: ${AWS_REGION}

  s3:
    bucket-name: ${AWS_S3_BUCKET_NAME}
```

Trong đó:

- `AWS_REGION`: Region triển khai dịch vụ AWS.
- `AWS_S3_BUCKET_NAME`: Tên Bucket Amazon S3 (`dental-service-images-huy`).

Backend sẽ sử dụng các thông tin này để kết nối tới Amazon S3 và thực hiện các thao tác upload, download và quản lý hình ảnh của hệ thống.

Sau khi hoàn tất cấu hình và khởi động ứng dụng, Backend có thể lưu trữ và truy xuất hình ảnh trực tiếp từ Amazon S3.