---
title : "Các bước chuẩn bị"
date : 2024-01-01
weight : 2
chapter : false
pre : " <b> 5.2. </b> "
---

Trong phần này, chúng ta sẽ chuẩn bị các tài nguyên AWS cần thiết để triển khai **Dental Clinic Management System**.

#### Chuẩn bị tài khoản AWS

Đăng nhập vào **AWS Management Console** và chọn Region **Asia Pacific (Singapore) - ap-southeast-1** để đảm bảo tất cả tài nguyên được triển khai trong cùng một khu vực.

#### Chuẩn bị IAM User

Tạo hoặc sử dụng IAM User **dental-backend-user** và gắn các AWS Managed Policies sau:

- AmazonEC2FullAccess
- AmazonDynamoDBFullAccess
- AmazonS3FullAccess
- AmazonSESFullAccess
- CloudWatchFullAccess
![create stack](/aws/images/5-Workshop/5.2-Prerequisite/IAM.png)
Các quyền này cho phép triển khai và quản lý các dịch vụ AWS được sử dụng trong hệ thống.

#### Chuẩn bị tài nguyên AWS

Trước khi triển khai ứng dụng, cần chuẩn bị các dịch vụ sau:

- Amazon EC2 để triển khai Backend Spring Boot.
- Amazon DynamoDB để lưu trữ dữ liệu.
- Amazon S3 để lưu trữ hình ảnh và tệp tin.
- Amazon SES để gửi email xác nhận lịch hẹn.
- Amazon CloudWatch để theo dõi log và giám sát hệ thống.
#### Chuẩn bị VPC

Trong workshop này, hệ thống sử dụng VPC **PVH** với dải mạng:

- **VPC name:** PVH
- **IPv4 CIDR:** 10.10.0.0/16
- **Region:** Asia Pacific (Singapore) - ap-southeast-1

VPC này là môi trường mạng riêng để triển khai các tài nguyên AWS của hệ thống như EC2, Subnet, Security Group và Route Table.

![VPC](/aws/images/5-Workshop/5.1-Workshop-overview/vpc.png)

#### Chuẩn bị Route Table

Route Table được sử dụng để điều hướng lưu lượng mạng giữa các Subnet và Internet Gateway.

Trong hệ thống, VPC **PVH** có các Route Table chính:

- **Route Table Public:** dùng cho Public Subnet, cho phép EC2 truy cập Internet thông qua Internet Gateway.
- **Route table-Private:** dùng cho Private Subnet, phục vụ các tài nguyên nội bộ.

Khi triển khai Backend trên EC2 và cần truy cập từ Internet, Instance nên được đặt trong **Public Subnet** và sử dụng **Route Table Public**.

![Route Table](/aws/images/5-Workshop/5.1-Workshop-overview/router.png)
#### Kiểm tra môi trường

Sau khi hoàn tất các bước trên, kiểm tra IAM User và các dịch vụ AWS đã sẵn sàng trước khi bắt đầu triển khai hệ thống ở các phần tiếp theo.