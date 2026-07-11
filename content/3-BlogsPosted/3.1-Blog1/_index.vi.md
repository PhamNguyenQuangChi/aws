---
title: "Blog 1"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---


# LOAD TESTING TRÊN AWS: KHÔNG CHỈ KIỂM TRA WEBSITE CHẠY ĐƯỢC, MÀ CÒN KIỂM TRA HỆ THỐNG CHỊU TẢI TỐT HAY KHÔNG
Khi xây dựng một website hoặc ứng dụng, nhiều người thường chỉ quan tâm đến việc hệ thống có chạy được, có truy cập được, có lỗi giao diện hay không.

Nhưng trong môi trường thực tế, đặc biệt là khi ứng dụng có nhiều người dùng cùng lúc, câu hỏi quan trọng hơn là: Nếu có hàng trăm hoặc hàng nghìn request gửi đến cùng lúc thì hệ thống có còn ổn định không?

Đây chính là lý do cần thực hiện Load Testing trước khi triển khai sản phẩm thật cho người dùng.

Để hỗ trợ bài toán này, AWS cung cấp giải pháp Distributed Load Testing on AWS, giúp mô phỏng lượng truy cập lớn, chạy kiểm thử tải phân tán và theo dõi kết quả trực tiếp trên các dịch vụ AWS.

NHỮNG ĐIỂM NỔI BẬT:
<br>&emsp;+Tạo kịch bản kiểm thử tải dễ dàng:
<br>&emsp;Người dùng có thể tạo các test scenario để mô phỏng nhiều request gửi đến website, API hoặc ứng dụng cần kiểm thử.
<br>&emsp;+Chạy kiểm thử bằng container:
<br>&emsp;Giải pháp sử dụng Amazon ECS trên AWS Fargate để chạy các container tạo tải. Điều này giúp hệ thống có thể mở rộng linh hoạt khi cần kiểm thử với số lượng request lớn hơn.
<br>&emsp;+Có giao diện web để quản lý:
<br>&emsp;Người dùng có thể tạo, chạy và theo dõi bài test thông qua giao diện web, thay vì phải thao tác hoàn toàn bằng dòng lệnh.
<br>&emsp;+Kết hợp nhiều dịch vụ AWS:
<br>&emsp;Kiến trúc sử dụng các dịch vụ như Amazon S3, CloudFront, API Gateway, AWS Lambda, Step Functions, DynamoDB, ECS Fargate và CloudWatch để tạo thành một hệ thống kiểm thử hoàn chỉnh.
<br>&emsp;+Theo dõi kết quả kiểm thử:
<br>&emsp;Sau khi chạy test, hệ thống có thể lưu kết quả, log và metrics để người dùng phân tích hiệu năng, phát hiện điểm nghẽn và đưa ra hướng tối ưu.

KẾT LUẬN:
Điều mình thấy hay ở Distributed Load Testing on AWS là giải pháp này giúp chúng ta kiểm tra khả năng chịu tải của hệ thống trước khi gặp traffic thật.
Một ứng dụng tốt không chỉ cần chạy được, mà còn cần trả lời được các câu hỏi như:
<br>&emsp;Hệ thống chịu được bao nhiêu người dùng cùng lúc?
<br>&emsp;API có bị chậm khi lượng request tăng không?
<br>&emsp;Thành phần nào đang là điểm nghẽn?
<br>&emsp;Có cần scale thêm tài nguyên hay không?
<br>&emsp;Hệ thống có ổn định khi chạy trong thời gian dài không?

Theo mình, đây là một chủ đề rất đáng học khi tìm hiểu về AWS, vì nó kết hợp nhiều mảng quan trọng như Container, Serverless, Monitoring, Performance Testing và Cloud Architecture.

Thông qua bài này, mình hiểu hơn rằng trước khi đưa một hệ thống lên production, việc kiểm thử tải là rất cần thiết để đảm bảo ứng dụng hoạt động ổn định, giảm rủi ro lỗi hệ thống và mang lại trải nghiệm tốt hơn cho người dùng.

Link tài liệu AWS có hình kiến trúc:
https://docs.aws.amazon.com/solutions/latest/distributed-load-testing-on-aws/architecture-overview.html

![Ảnh](/aws/images/3-BlogsPosted/Blog1.jpg)