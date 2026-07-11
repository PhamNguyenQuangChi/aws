---
title : "Cấu hình Amazon SES & SNS"
date : 2024-01-01
weight : 5
chapter : false
pre : " <b> 5.5. </b> "
---

Trong **Dental Clinic Management System**, **Amazon SES** được sử dụng để gửi email xác nhận lịch hẹn và các thông báo đến người dùng, trong khi **Amazon SNS** được sử dụng để quản lý các thông báo thông qua mô hình Publish/Subscribe.

### 1. Cấu hình Amazon SES

Đăng nhập vào **AWS Management Console**, tìm kiếm **Amazon SES** và chọn **Configuration → Identities**.

Chọn **Create identity**, sau đó chọn **Email address** và nhập địa chỉ email sẽ được sử dụng để gửi thông báo từ hệ thống.

![Amazon SES Identity](/aws/images/5-Workshop/5.1-Workshop-overview/SES.png)

Sau khi tạo thành công, AWS sẽ gửi một email xác minh đến địa chỉ đã đăng ký. Mở email và chọn **Verify email address** để hoàn tất quá trình xác minh.

---

### 2. Cấu hình Amazon SNS

Đăng nhập vào **AWS Management Console**, tìm kiếm **Amazon SNS** và chọn **Topics**.

Chọn **Create topic**, chọn loại **Standard** và đặt tên Topic là:

```text
dental-clinic-notification
```

Sau đó nhấn **Create topic** để tạo Topic.

![Amazon SNS Topic](/aws/images/5-Workshop/5.1-Workshop-overview/SNS.png)

Sau khi tạo thành công, hệ thống sẽ cấp một **Topic ARN**, được sử dụng để Backend gửi thông báo đến Amazon SNS.

---

### 3. Cấu hình Backend

Cập nhật file `application.yml` để khai báo các thông tin cần thiết:

```yaml
aws:
  region: ${AWS_REGION}

  ses:
    sender-email: ${AWS_SES_SENDER_EMAIL}

  sns:
    topic-arn: ${AWS_SNS_TOPIC_ARN}
```

Trong đó:

- `AWS_SES_SENDER_EMAIL`: Địa chỉ email đã được xác minh trên Amazon SES.
- `AWS_SNS_TOPIC_ARN`: ARN của Topic đã tạo trên Amazon SNS.

Sau khi hoàn tất cấu hình và khởi động lại Backend, hệ thống đã sẵn sàng gửi email thông qua Amazon SES và phát thông báo thông qua Amazon SNS.