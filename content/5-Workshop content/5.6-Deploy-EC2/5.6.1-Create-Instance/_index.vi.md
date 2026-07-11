---
title : "Tạo EC2 Instance"
date : 2024-01-01
weight : 1
chapter : false
pre : " <b> 5.6.1. </b> "
---

Trong bước này, chúng ta sẽ tạo một **Amazon EC2 Instance** để triển khai Backend Spring Boot của hệ thống **Dental Clinic Management System**.

### Truy cập Amazon EC2

Đăng nhập vào **AWS Management Console**, tìm kiếm **EC2** và chọn dịch vụ **EC2**.

Tại menu bên trái, chọn **Instances**, sau đó nhấn **Launch instances** để bắt đầu tạo máy chủ mới.

### Cấu hình tên Instance

Tại phần **Name and tags**, nhập tên Instance:

```text
Dental-Backend
```

Tên này giúp dễ dàng nhận biết máy chủ dùng để triển khai Backend của hệ thống.

### Chọn hệ điều hành

Tại phần **Application and OS Images (Amazon Machine Image)**, chọn:

```text
Amazon Linux 2023 AMI
```

AMI này cung cấp môi trường Linux ổn định để cài đặt Docker và chạy ứng dụng Backend.

### Chọn Instance Type

Tại phần **Instance type**, chọn:

```text
t3.micro
```

Instance type này phù hợp cho môi trường thực hành và triển khai thử nghiệm.

### Chọn Key Pair

Tại phần **Key pair (login)**, chọn Key Pair đã tạo trước đó:

```text
keydental
```

Key Pair này được sử dụng để kết nối SSH vào EC2 Instance sau khi máy chủ được khởi tạo.

![EC2 Configuration](/aws/images/5-Workshop/5.1-Workshop-overview/EC2p1.png)

### Cấu hình Security Group

Tại phần **Network settings**, tạo Security Group mới hoặc sử dụng Security Group có sẵn.

Trong workshop này, Security Group được cấu hình mở các cổng cần thiết:

| Type | Port | Mục đích |
|------|------|----------|
| SSH | 22 | Kết nối SSH vào EC2 |
| HTTP | 80 | Truy cập ứng dụng thông qua HTTP |
| Custom TCP | 8080 | Truy cập Backend Spring Boot |

Source được cấu hình là:

```text
0.0.0.0/0
```

để cho phép truy cập từ Internet trong môi trường thực hành.

![EC2 Security Group](/aws/images/5-Workshop/5.1-Workshop-overview/EC2p2.png)

### Khởi tạo EC2 Instance

Sau khi hoàn tất các cấu hình, kiểm tra lại phần **Summary** ở bên phải màn hình.

Nếu các thông tin đã đúng, nhấn **Launch instance** để tạo EC2 Instance.

Khi khởi tạo thành công, AWS sẽ hiển thị thông báo **Successfully initiated launch of instance**.

### Kiểm tra Instance

Quay lại trang **Instances** để kiểm tra trạng thái của EC2 Instance.

Khi Instance chuyển sang trạng thái **Running** và **Status check** hiển thị thành công, EC2 đã sẵn sàng để sử dụng.

![EC2 Running](/aws/images/5-Workshop/5.1-Workshop-overview/EC2p3.png)

Sau khi hoàn tất bước này, chúng ta đã tạo thành công EC2 Instance dùng để triển khai Backend Spring Boot của hệ thống.