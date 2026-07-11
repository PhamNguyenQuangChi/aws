---
title : "Triển khai Backend trên EC2"
date : 2024-01-01
weight : 6
chapter : false
pre : " <b> 5.6. </b> "
---

Trong phần này, chúng ta sẽ triển khai **Backend Spring Boot** của **Dental Clinic Management System** lên **Amazon EC2**. Sau khi triển khai thành công, Backend sẽ kết nối với các dịch vụ AWS như **Amazon DynamoDB**, **Amazon S3**, **Amazon SES** và **Amazon SNS** để cung cấp đầy đủ các chức năng của hệ thống.

---

### 5.6.1. Tạo EC2 Instance

Đăng nhập vào **AWS Management Console**, tìm kiếm **Amazon EC2** và chọn **Launch Instance**.

Cấu hình EC2 như sau:

- **Name:** Dental-Backend
- **Amazon Machine Image (AMI):** Amazon Linux 2023
- **Instance type:** t3.micro
- **Key pair:** Sử dụng hoặc tạo mới Key Pair để kết nối SSH.
- **Security Group:**
  - SSH (22)
  - HTTP (80)
  - Custom TCP (8080)

Sau khi hoàn tất cấu hình, nhấn **Launch Instance** để tạo máy chủ EC2.

![Create EC2](/images/5-Workshop/5.1-Workshop-overview/EC2p3.png)

---

### 5.6.2. Kết nối EC2

Sau khi EC2 chuyển sang trạng thái **Running**, sử dụng **EC2 Instance Connect** hoặc SSH để kết nối đến máy chủ.

Ví dụ:

```bash
ssh -i keydental.pem ec2-user@<Public-IP>
```

Sau khi kết nối thành công, cập nhật hệ thống và cài đặt Docker để chuẩn bị triển khai ứng dụng.


---

### 5.6.3. Triển khai Backend

Upload source code hoặc Docker Image của Backend lên EC2.

Tiếp theo, khởi động ứng dụng bằng Docker:

```bash
docker build -t dental-backend .
docker run -d -p 8080:8080 --env-file .env dental-backend
```

Sau khi ứng dụng khởi động thành công, Backend sẽ tự động kết nối đến:

- Amazon DynamoDB
- Amazon S3
- Amazon SES
- Amazon SNS

để xử lý lưu trữ dữ liệu, quản lý hình ảnh và gửi email thông báo.


---

### 5.6.4. Kiểm tra hệ thống

Sau khi triển khai hoàn tất, truy cập Backend thông qua địa chỉ Public IP của EC2:

```text
http://<Public-IP>:8080
```

Hoặc sử dụng **Postman** để kiểm tra các API của hệ thống.

Nếu Backend phản hồi thành công và có thể truy cập dữ liệu từ Amazon DynamoDB, tải hình ảnh lên Amazon S3, đồng thời gửi email thông qua Amazon SES và Amazon SNS thì quá trình triển khai đã hoàn tất.
