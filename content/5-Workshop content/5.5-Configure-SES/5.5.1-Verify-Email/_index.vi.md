---
title : "Xác minh Email"
date : 2024-01-01
weight : 1
chapter : false
pre : " <b> 5.5.1. </b> "
---

Trong phần này, chúng ta sẽ cấu hình **Amazon Simple Notification Service (SNS)** để gửi thông báo từ hệ thống **Dental Clinic Management System** thông qua một SNS Topic.

### 1. Tạo SNS Topic

Đăng nhập vào **AWS Management Console**, tìm kiếm **Amazon SNS** và chọn **Topics**.

Chọn **Create topic** và cấu hình các thông tin sau:

- **Type:** Standard
- **Name:** `dental-clinic-notification`

Giữ nguyên các thiết lập mặc định và chọn **Create topic**.

---

### 2. Tạo Subscription

Sau khi Topic được tạo, tiến hành đăng ký địa chỉ email để nhận thông báo.

1. Mở Topic vừa tạo.
2. Chọn **Create subscription**.
3. Tại **Protocol**, chọn **Email**.
4. Tại **Endpoint**, nhập địa chỉ email sẽ nhận thông báo.
5. Chọn **Create subscription**.

---

### 3. Xác nhận Subscription

Amazon SNS sẽ gửi một email xác nhận đến địa chỉ email đã đăng ký.

Mở email và chọn **Confirm subscription** để hoàn tất quá trình đăng ký.

Sau khi xác nhận thành công, trạng thái của Subscription sẽ chuyển sang **Confirmed**.

---

### 4. Kiểm tra gửi thông báo

Tại giao diện của Topic, chọn **Publish message**.

Nhập các thông tin kiểm tra:

- **Subject:** Dental Clinic Notification
- **Message:** Test notification from Dental Clinic Management System.

Sau đó chọn **Publish message**.

Nếu cấu hình thành công, địa chỉ email đã đăng ký sẽ nhận được thông báo từ Amazon SNS.

Đến đây, Amazon SNS đã sẵn sàng để tích hợp với Backend nhằm gửi các thông báo của **Dental Clinic Management System**.
