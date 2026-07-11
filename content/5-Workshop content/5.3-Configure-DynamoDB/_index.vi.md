---
title : "Cấu hình DynamoDB"
date : 2024-01-01
weight : 3
chapter : false
pre : " <b> 5.3. </b> "
---

Trong bước này, chúng ta sẽ kiểm tra các bảng **Amazon DynamoDB** được sử dụng trong **Dental Clinic Management System**.

Đăng nhập vào **AWS Management Console**, tìm kiếm dịch vụ **DynamoDB** và chọn **Tables**.

Tại đây, các bảng dữ liệu của hệ thống đã được tạo và sẵn sàng sử dụng.

Các bảng chính của hệ thống bao gồm:

| Table | Chức năng |
|-------|-----------|
| users | Lưu thông tin tài khoản người dùng |
| doctors | Lưu thông tin bác sĩ |
| specialties | Lưu chuyên khoa |
| services | Lưu thông tin dịch vụ |
| appointments | Lưu lịch hẹn khám |
| doctor_schedules | Lưu lịch làm việc của bác sĩ |
| consultations | Lưu yêu cầu tư vấn |
| invoices | Lưu thông tin hóa đơn |
| feedbacks | Lưu đánh giá của bệnh nhân |
| blogs | Lưu bài viết |
| categories | Lưu danh mục bài viết |
| clinics | Lưu thông tin phòng khám |


![DynamoDB Tables](/aws/images/5-Workshop/5.1-Workshop-overview/dynamodb-tables.png)

Kiểm tra trạng thái của các bảng và đảm bảo tất cả đều ở trạng thái **Active** trước khi tiếp tục triển khai hệ thống.