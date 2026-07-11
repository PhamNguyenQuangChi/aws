---
title : "Dọn dẹp tài nguyên"
date : 2024-01-01
weight : 8
chapter : false
pre : " <b> 5.8. </b> "
---

Sau khi hoàn thành Workshop và kiểm tra hệ thống hoạt động thành công, bước cuối cùng là dọn dẹp các tài nguyên đã tạo trên AWS nhằm tránh phát sinh chi phí không cần thiết.

Trong phần này, chúng ta sẽ lần lượt xóa các tài nguyên đã sử dụng trong quá trình triển khai **Dental Clinic Management System**. 

### 5.8.1. Xóa EC2 Instance

1. Truy cập **Amazon EC2**.
2. Chọn **Instances**.
3. Chọn EC2 Instance đã tạo.
4. Chọn **Instance state → Terminate instance**.
5. Xác nhận thao tác xóa.

![Terminate EC2](/images/5-Workshop/5.1-Workshop-overview/xoaEC2.png)

---

### 5.8.2. Xóa Amazon S3 Bucket

1. Truy cập **Amazon S3**.
2. Chọn Bucket của dự án.
3. Xóa toàn bộ các đối tượng (Objects) trong Bucket.
4. Sau đó chọn **Delete bucket**.
5. Nhập tên Bucket để xác nhận và hoàn tất việc xóa.

> **Lưu ý:** Trong Workshop này, nhóm **không thực hiện xóa Amazon S3 Bucket** vì Bucket vẫn được sử dụng để lưu trữ hình ảnh của hệ thống và phục vụ cho quá trình phát triển, kiểm thử trong các giai đoạn tiếp theo.



---

### 5.8.3. Xóa bảng Amazon DynamoDB

1. Truy cập **Amazon DynamoDB**.
2. Chọn **Tables**.
3. Chọn các bảng của dự án như:
   - users
   - doctors
   - services
   - appointments
   - invoices
   - feedbacks
   - consultations
   - clinics
4. Chọn **Delete table**.
5. Nhập xác nhận và hoàn tất thao tác xóa.

> **Lưu ý:** Trong Workshop này, nhóm **không thực hiện xóa các bảng Amazon DynamoDB** vì dữ liệu vẫn còn được sử dụng cho quá trình phát triển, kiểm thử và demo hệ thống.


### 5.8.5. Xóa Amazon SES Identity

1. Truy cập **Amazon SES**.
2. Chọn **Configuration → Identities**.
3. Chọn Email Identity đã xác minh.
4. Chọn **Delete** để xóa Identity.

> **Lưu ý:** Trong Workshop này, nhóm **không thực hiện xóa Email Identity trên Amazon SES** vì vẫn tiếp tục sử dụng để gửi email xác nhận lịch hẹn và các thông báo từ hệ thống.




### 5.8.5. Xóa Amazon SES Identity

1. Truy cập **Amazon SES**.
2. Chọn **Configuration → Identities**.
3. Chọn Email Identity đã xác minh.
4. Chọn **Delete** để xóa Identity.

> **Lưu ý:** Trong Workshop này, nhóm **không thực hiện xóa Email Identity trên Amazon SES** vì vẫn tiếp tục sử dụng để gửi email xác nhận lịch hẹn và các thông báo từ hệ thống.

Sau khi hoàn thành các bước trên, toàn bộ tài nguyên được sử dụng trong Workshop đã được dọn dẹp. Điều này giúp tránh phát sinh chi phí và giữ cho tài khoản AWS luôn gọn gàng, sẵn sàng cho các lần triển khai tiếp theo.