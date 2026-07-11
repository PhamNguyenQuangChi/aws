---
title : "Cấu hình quyền truy cập"
date : 2024-01-01
weight : 2
chapter : false
pre : " <b> 5.4.2. </b> "
---

Trong hệ thống **Dental Clinic Management System**, việc bảo mật dữ liệu hình ảnh (như ảnh cá nhân của bác sĩ, bệnh nhân) là rất quan trọng. Do đó, hệ thống không mở quyền truy cập công khai (Public Access) mà sử dụng cơ chế cấp quyền truy cập động thông qua Backend.

### 1. Chính sách bảo mật của Bucket

Ở bước tạo Bucket, chúng ta đã giữ nguyên thiết lập mặc định là **Block all public access** (Chặn tất cả truy cập công khai).

Điều này có nghĩa là không ai trên Internet có thể xem hoặc tải trực tiếp ảnh từ Amazon S3 bằng URL gốc. Nếu cố tình truy cập, Amazon S3 sẽ chặn và trả về lỗi **Access Denied**. 

Chỉ có ứng dụng Backend (thông qua IAM User `dental-backend-user` với quyền `AmazonS3FullAccess`) mới có thể giao tiếp, đọc và ghi file vào Bucket này một cách hợp lệ.

### 2. Cấp quyền hiển thị bằng Pre-signed URL

Để Frontend (ReactJS) có thể hiển thị được hình ảnh cho người dùng, Backend Spring Boot sẽ đóng vai trò trung gian cấp quyền thông qua cơ chế **Pre-signed URL** (Đường dẫn có chữ ký số xác thực).

Trong mã nguồn Backend, class `AwsConfig` đã khởi tạo Bean `S3Presigner`:

```java
    @Bean
    public S3Presigner s3Presigner(AwsCredentialsProvider credentialsProvider) {
        return S3Presigner.builder()
                .region(Region.of(region))
                .credentialsProvider(credentialsProvider)
                .build();
    }
