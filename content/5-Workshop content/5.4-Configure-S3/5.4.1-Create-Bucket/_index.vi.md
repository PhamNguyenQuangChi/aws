---
title : "Tạo S3 Bucket"
date : 2024-01-01
weight : 1
chapter : false
pre : " <b> 5.4.1. </b> "
---

Trong bước này, chúng ta sẽ tạo một **Amazon S3 Bucket** để lưu trữ hình ảnh của hệ thống **Dental Clinic Management System**.

### Tạo S3 Bucket

1. Đăng nhập vào **AWS Management Console**.
2. Tìm kiếm **Amazon S3**.
3. Chọn **Buckets**.
4. Chọn **Create bucket**.
5. Cấu hình Bucket với các thông tin sau:
   - **Bucket name:** `dental-service-images-huy`
   - **AWS Region:** `Asia Pacific (Singapore) - ap-southeast-1`
6. Giữ nguyên các thiết lập mặc định và chọn **Create bucket**.

Sau khi tạo thành công, Bucket sẽ xuất hiện trong danh sách Buckets của Amazon S3.

![Amazon S3 Bucket](/images/5-Workshop/5.1-Workshop-overview/S3.png)

### Kiểm tra Bucket

Chọn Bucket **dental-service-images-huy** để kiểm tra các đối tượng lưu trữ.

Trong Bucket, hệ thống đã tổ chức các thư mục để quản lý hình ảnh theo từng chức năng:

- **avatars/**: Lưu ảnh đại diện.
- **clinics/**: Lưu hình ảnh phòng khám.
- **services/**: Lưu hình ảnh dịch vụ.

![Amazon S3 Objects](/images/5-Workshop/5.1-Workshop-overview/s3-objects.png)

### Kiểm tra CloudFront

Sau khi tạo thành công, trạng thái của Distribution sẽ chuyển sang **Enabled**.

Sao chép **Domain name** của CloudFront để sử dụng trong Backend hoặc Frontend khi truy cập hình ảnh.

![CloudFront Running](/images/5-Workshop/5.1-Workshop-overview/cloufront.png)

Sau khi hoàn thành bước này, hệ thống sẽ sử dụng CloudFront để phân phối hình ảnh từ Amazon S3, giúp tăng tốc độ tải và cải thiện hiệu năng truy cập.
Sau khi hoàn tất bước này, Amazon S3 đã sẵn sàng để Backend lưu trữ và truy xuất hình ảnh của hệ thống.