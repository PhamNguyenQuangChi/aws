---
title : "Kiểm tra hệ thống"
date : 2024-01-01
weight : 7
chapter : false
pre : " <b> 5.7. </b> "
---

Sau khi hoàn tất việc triển khai **Dental Clinic Management System** lên AWS, bước cuối cùng là kiểm tra toàn bộ hệ thống để đảm bảo các dịch vụ hoạt động ổn định và có thể giao tiếp với nhau.

Trong phần này, chúng ta sẽ xác minh rằng Backend trên Amazon EC2 đã kết nối thành công với Amazon DynamoDB, Amazon S3, Amazon SES và Amazon SNS, đồng thời kiểm tra các chức năng chính của hệ thống.

### 5.7.1. Kiểm tra trạng thái EC2

Đầu tiên, truy cập **Amazon EC2 Console** và kiểm tra trạng thái của Instance.

Nếu Instance hiển thị trạng thái **Running** và vượt qua tất cả các **Status Checks**, điều đó cho thấy máy chủ đã sẵn sàng để chạy ứng dụng Backend.

![EC2 Running](/images/5-Workshop/5.1-Workshop-overview/EC2p3.png)

---

### 5.7.2. Kiểm tra lưu trữ dữ liệu

Đăng nhập vào hệ thống và tạo mới hoặc cập nhật dữ liệu.

Sau đó truy cập **Amazon DynamoDB** để xác nhận dữ liệu đã được lưu thành công vào các bảng của hệ thống.

![DynamoDB](/images/5-Workshop/5.1-Workshop-overview/database.png)

---

### 5.7.3. Kiểm tra Upload hình ảnh

Thực hiện tải lên ảnh đại diện hoặc ảnh dịch vụ từ giao diện hệ thống.

Sau khi upload thành công, truy cập **Amazon S3** và kiểm tra Bucket để xác nhận tệp hình ảnh đã được lưu.

![Amazon S3](/images/5-Workshop/5.1-Workshop-overview/s3avata.png)

---

### 5.7.4. Kiểm tra gửi Email

Tiến hành đặt lịch khám hoặc thực hiện chức năng gửi email từ hệ thống.

Nếu người dùng nhận được email thông báo trong Gmail, chứng tỏ Amazon SES đã được cấu hình và hoạt động chính xác.

![Amazon SES](/images/5-Workshop/5.1-Workshop-overview/nhangmail.png)

---


Sau khi hoàn thành các bước kiểm tra trên, hệ thống **Dental Clinic Management System** đã được triển khai thành công trên nền tảng AWS. Backend hoạt động ổn định trên Amazon EC2 và có thể kết nối với Amazon DynamoDB, Amazon S3, Amazon SES và Amazon SNS để đáp ứng đầy đủ các chức năng của hệ thống.