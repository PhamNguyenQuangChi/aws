---
title : "Giới thiệu"
date : 2024-01-01
weight : 1
chapter : false
pre : " <b> 5.1. </b> "
---

#### Giới thiệu về hệ thống

**Dental Clinic Management System** là hệ thống website hỗ trợ quản lý phòng khám nha khoa và đặt lịch khám trực tuyến, được triển khai trên nền tảng **Amazon Web Services (AWS)**. Hệ thống cho phép bệnh nhân đăng ký tài khoản, đặt lịch khám, xem thông tin dịch vụ và bác sĩ, đồng thời giúp quản trị viên quản lý lịch hẹn, dịch vụ, bác sĩ và thông tin bệnh nhân trên một nền tảng tập trung.

Hệ thống được xây dựng theo mô hình **3-Tier Architecture**, giúp tách biệt giữa giao diện người dùng (Frontend), tầng xử lý nghiệp vụ (Backend) và tầng lưu trữ dữ liệu (Database). Kiến trúc này giúp ứng dụng dễ bảo trì, dễ mở rộng và nâng cao hiệu năng khi triển khai trên môi trường Cloud.

#### Tổng quan về workshop

Trong workshop này, chúng ta sẽ triển khai toàn bộ hệ thống **Dental Clinic Management System** trên AWS bằng cách sử dụng nhiều dịch vụ khác nhau.

- **Frontend Layer:** Ứng dụng ReactJS được triển khai bằng **AWS Amplify**, kết hợp với **Amazon CloudFront** để phân phối nội dung và **Amazon Route 53** để quản lý tên miền. **AWS WAF** được sử dụng để bảo vệ ứng dụng trước các cuộc tấn công phổ biến trên Web.

- **Application Layer:** Ứng dụng Backend được phát triển bằng **Spring Boot** và triển khai trên **Amazon EC2**. **Application Load Balancer (ALB)** tiếp nhận và phân phối lưu lượng truy cập đến máy chủ Backend nhằm đảm bảo tính sẵn sàng và khả năng mở rộng.

- **Data Layer:** Dữ liệu của hệ thống được lưu trữ trên **Amazon DynamoDB**, trong khi hình ảnh bác sĩ, hình ảnh dịch vụ và các tệp tải lên được lưu trên **Amazon S3**.

- **Security & Monitoring:** **AWS IAM** quản lý quyền truy cập vào tài nguyên AWS, **AWS Secrets Manager** lưu trữ các thông tin nhạy cảm, **AWS KMS** mã hóa dữ liệu, **Amazon CloudWatch** giám sát hoạt động của hệ thống, còn **Amazon SNS** và **Amazon SES** được sử dụng để gửi thông báo và email xác nhận đặt lịch cho người dùng.

Thông qua workshop này, người đọc sẽ được hướng dẫn từng bước triển khai hệ thống từ chuẩn bị môi trường AWS, triển khai Frontend và Backend, cấu hình cơ sở dữ liệu, thiết lập các dịch vụ bảo mật, giám sát hoạt động của hệ thống, cho đến kiểm thử và dọn dẹp tài nguyên sau khi hoàn thành.

![AWS Architecture](/FCJ_Group_5_AE_C6/images/5-Workshop/5.1-Workshop-overview/drawio.png)