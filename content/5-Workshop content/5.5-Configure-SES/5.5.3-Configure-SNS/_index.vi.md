---
title : "Cấu hình SNS gửi thông báo"
date : 2024-01-01
weight : 3
chapter : false
pre : " <b> 5.5.3. </b> "
---

Trong phần này, chúng ta sẽ cấu hình **Amazon SNS (Simple Notification Service)** để tự động gửi email thông báo (ví dụ: cảnh báo hệ thống, báo cáo) về địa chỉ Gmail của bạn.

### 1. Tạo SNS Topic

1. Truy cập **AWS Management Console**, tìm kiếm **Amazon SNS** và chọn **Topics**.
2. Nhấn nút **Create topic**.
3. Tại phần **Type**, chọn **Standard**.
4. Nhập **Name** (ví dụ: dental-system-alerts).
5. Giữ nguyên các thông số mặc định và nhấn **Create topic.

### 2. Đăng ký (Subscribe) Gmail nhận thông báo

Sau khi Topic được tạo, chúng ta cần thêm email sẽ nhận thông báo:

1. Trong giao diện chi tiết của Topic vừa tạo, chuyển sang tab **Subscriptions** và nhấn **Create subscription**.
2. Tại ô **Protocol**, chọn **Email**.
3. Tại ô **Endpoint**, nhập địa chỉ **Gmail** của bạn (ví dụ: your-email@gmail.com).
4. Nhấn **Create subscription**.

### 3. Xác nhận đăng ký (Confirm Subscription)

1. AWS SNS sẽ gửi một email xác nhận đến địa chỉ Gmail bạn vừa nhập.
2. Mở hộp thư Gmail, tìm email có tiêu đề **AWS Notification - Subscription Confirmation**.
3. Nhấn vào đường link **Confirm subscription** trong email.
4. Quay lại AWS Console, kiểm tra Subscription sẽ chuyển từ trạng thái *Pending confirmation* sang **Confirmed**.

### 4. Gửi thử thông báo (Publish Message)

1. Tại giao diện Topic trên AWS, nhấn nút **Publish message**.
2. Nhập **Subject** (ví dụ: Test Alert từ Hệ thống Nha khoa).
3. Nhập nội dung vào ô **Message body to send to the endpoint** (ví dụ: Hệ thống hoạt động bình thường!).
4. Kéo xuống dưới cùng và nhấn **Publish message**.
5. Kiểm tra hộp thư Gmail, bạn sẽ nhận được nội dung vừa gửi.

Hệ thống SNS lúc này đã sẵn sàng để tích hợp với CloudWatch hoặc Backend để tự động gửi thông báo.
