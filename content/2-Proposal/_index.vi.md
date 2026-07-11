---
title: "Bản đề xuất"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

# Dental Clinic Management System
## Website đặt lịch và quản lý phòng khám nha khoa trên nền tảng AWS Cloud

### 1. Tóm tắt điều hành

Dental Clinic System là hệ thống website giúp bệnh nhân dễ dàng đặt lịch khám nha khoa trực tuyến, tra cứu dịch vụ, theo dõi lịch hẹn và nhận thông báo từ phòng khám. Đồng thời, hệ thống hỗ trợ bác sĩ và quản trị viên quản lý lịch khám, dịch vụ, hồ sơ bệnh nhân và hoạt động của phòng khám.

Hệ thống được xây dựng theo kiến trúc Cloud Native trên AWS nhằm đảm bảo tính bảo mật, khả năng mở rộng và hiệu năng cao. Frontend được triển khai bằng React thông qua AWS Amplify, Backend sử dụng Spring Boot chạy trên Amazon EC2, dữ liệu lưu trữ trên Amazon DynamoDB và Amazon S3, kết hợp các dịch vụ CloudWatch, SNS, SES, WAF và Secrets Manager để đảm bảo vận hành ổn định.

---

### 2. Tuyên bố vấn đề

#### Vấn đề hiện tại

Hiện nay nhiều phòng khám nha khoa vẫn quản lý lịch khám bằng điện thoại hoặc ghi chép thủ công, dẫn đến:

- Khó quản lý lịch hẹn.
- Dễ xảy ra trùng lịch khám.
- Khó theo dõi thông tin bệnh nhân.
- Thiếu hệ thống thông báo tự động.
- Khó mở rộng khi số lượng người dùng tăng.

#### Giải pháp

Dental Clinic System cung cấp nền tảng đặt lịch trực tuyến hoạt động trên AWS Cloud.

Người dùng có thể:

- Đăng ký, đăng nhập.
- Đặt lịch khám.
- Xem lịch hẹn.
- Hủy lịch.
- Xem dịch vụ.
- Theo dõi trạng thái lịch khám.

Bác sĩ có thể:

- Xem lịch làm việc.
- Quản lý lịch khám.
- Cập nhật trạng thái khám.

Quản trị viên có thể:

- Quản lý người dùng.
- Quản lý bác sĩ.
- Quản lý dịch vụ.
- Quản lý lịch hẹn.
- Theo dõi hoạt động hệ thống.

#### Lợi ích

- Giảm thời gian tiếp nhận bệnh nhân.
- Tự động hóa quy trình đặt lịch.
- Nâng cao trải nghiệm khách hàng.
- Dễ dàng mở rộng hệ thống.
- Tăng tính bảo mật dữ liệu.
- Giảm chi phí vận hành nhờ sử dụng dịch vụ AWS.

---

### 3. Kiến trúc giải pháp

Hệ thống được xây dựng theo mô hình Cloud Native trên AWS.

Frontend được triển khai trên AWS Amplify, kết hợp Amazon Route 53, CloudFront và AWS WAF để tăng tốc truy cập và bảo vệ ứng dụng.

Backend sử dụng Spring Boot triển khai trên Amazon EC2 phía sau Application Load Balancer (ALB).

Dữ liệu được lưu trên Amazon DynamoDB và hình ảnh được lưu trữ trên Amazon S3.

Thông tin nhạy cảm được quản lý bởi AWS Secrets Manager và AWS KMS.

CloudWatch theo dõi hoạt động hệ thống, SNS và Amazon SES gửi cảnh báo cũng như email xác nhận đặt lịch.

![Dental Clinic Architecture](/aws/images/2-Proposal/Proposal.jpg)

### Dịch vụ AWS sử dụng

- **Amazon Route 53:** Quản lý tên miền và định tuyến người dùng đến hệ thống thông qua DNS.
- **Amazon CloudFront:** Phân phối nội dung (CDN), tăng tốc độ truy cập và giảm độ trễ cho website.
- **AWS WAF:** Bảo vệ ứng dụng web trước các cuộc tấn công phổ biến như SQL Injection, Cross-Site Scripting (XSS) và giới hạn lưu lượng truy cập bất thường.
- **AWS Amplify:** Triển khai và lưu trữ ứng dụng Frontend React, tự động build và triển khai khi có thay đổi từ GitHub.
- **Application Load Balancer (ALB):** Tiếp nhận và phân phối lưu lượng truy cập đến máy chủ Backend, giúp tăng tính sẵn sàng và khả năng mở rộng.
- **Amazon EC2:** Chạy ứng dụng Backend được xây dựng bằng Spring Boot, xử lý các API và nghiệp vụ của hệ thống.
- **Amazon DynamoDB:** Lưu trữ dữ liệu của hệ thống như tài khoản người dùng, bác sĩ, dịch vụ, lịch hẹn và thông tin đặt khám.
- **Amazon S3:** Lưu trữ hình ảnh bác sĩ, hình ảnh dịch vụ, ảnh đại diện và các tệp tải lên từ người dùng.
- **AWS Secrets Manager:** Quản lý và lưu trữ an toàn các thông tin nhạy cảm như JWT Secret, Access Key và các thông số kết nối.
- **AWS Key Management Service (KMS):** Mã hóa dữ liệu và quản lý khóa bảo mật nhằm tăng cường an toàn thông tin.
- **Amazon CloudWatch:** Giám sát tài nguyên AWS, thu thập log và theo dõi hiệu năng của hệ thống.
- **Amazon SNS:** Gửi thông báo khi xảy ra sự kiện hoặc cảnh báo hệ thống đến quản trị viên.
- **Amazon SES:** Gửi email xác nhận đặt lịch, thông báo thay đổi lịch khám và các email hỗ trợ người dùng.
- **AWS Identity and Access Management (IAM):** Quản lý người dùng, vai trò và phân quyền truy cập các tài nguyên AWS theo nguyên tắc bảo mật.
### Thiết kế thành phần

**Frontend**

- ReactJS
- AWS Amplify
- CloudFront
- Route53
- AWS WAF

**Backend**

- Spring Boot
- Amazon EC2
- Application Load Balancer

**Database**

- Amazon DynamoDB

**Storage**

- Amazon S3

**Security**

- IAM
- Secrets Manager
- AWS KMS

**Monitoring**

- CloudWatch
- SNS
- SES

---

### 4. Triển khai kỹ thuật

#### Các giai đoạn triển khai

Dự án được chia thành 4 giai đoạn chính, từ phân tích yêu cầu đến triển khai hệ thống trên nền tảng AWS Cloud.

1. **Phân tích yêu cầu và thiết kế hệ thống:** Khảo sát nhu cầu của phòng khám nha khoa, phân tích các chức năng cần thiết như quản lý người dùng, bác sĩ, dịch vụ và lịch hẹn. Thiết kế cơ sở dữ liệu, giao diện người dùng và kiến trúc triển khai trên AWS Cloud.

2. **Xây dựng và phát triển hệ thống:** Phát triển Frontend bằng ReactJS và Backend bằng Java Spring Boot theo mô hình RESTful API. Đồng thời xây dựng cơ sở dữ liệu trên Amazon DynamoDB, lưu trữ hình ảnh trên Amazon S3 và hoàn thiện các chức năng nghiệp vụ của hệ thống.

3. **Triển khai hệ thống trên AWS:** Triển khai ứng dụng Frontend bằng AWS Amplify, triển khai Backend trên Amazon EC2, cấu hình Application Load Balancer (ALB), Route 53, CloudFront và AWS WAF để đảm bảo khả năng truy cập, bảo mật và hiệu năng của hệ thống.

4. **Kiểm thử, tối ưu và vận hành:** Tiến hành kiểm thử chức năng, kiểm thử bảo mật và hiệu năng. Theo dõi hệ thống bằng Amazon CloudWatch, cấu hình Amazon SNS và Amazon SES để gửi thông báo và email xác nhận lịch hẹn, đồng thời tối ưu chi phí và hiệu năng trước khi đưa hệ thống vào sử dụng.

---

#### Yêu cầu kỹ thuật

**Frontend**

- Phát triển bằng **ReactJS** kết hợp **Tailwind CSS** để xây dựng giao diện người dùng hiện đại và thân thiện.
- Sử dụng **Axios** để giao tiếp với RESTful API.
- Triển khai ứng dụng trên **AWS Amplify**.
- Tăng tốc truy cập thông qua **Amazon CloudFront** và định tuyến tên miền bằng **Amazon Route 53**.
- Bảo vệ ứng dụng bằng **AWS WAF** nhằm hạn chế các cuộc tấn công phổ biến như SQL Injection và Cross-Site Scripting (XSS).

**Backend**

- Phát triển bằng **Java Spring Boot** theo mô hình RESTful API.
- Xác thực và phân quyền người dùng bằng **JWT Authentication**.
- Triển khai Backend trên **Amazon EC2**.
- Sử dụng **Application Load Balancer (ALB)** để phân phối lưu lượng truy cập và tăng tính sẵn sàng của hệ thống.
- Quản lý thông tin bảo mật bằng **AWS Secrets Manager** và mã hóa dữ liệu với **AWS KMS**.

**Cơ sở dữ liệu và lưu trữ**

- **Amazon DynamoDB** được sử dụng để lưu trữ dữ liệu người dùng, bác sĩ, dịch vụ, lịch hẹn và thông tin đặt khám.
- **Amazon S3** lưu trữ hình ảnh bác sĩ, hình ảnh dịch vụ, ảnh đại diện và các tệp do người dùng tải lên.

**Giám sát và thông báo**

- **Amazon CloudWatch** theo dõi log, tài nguyên và hiệu năng của hệ thống.
- **Amazon SNS** gửi cảnh báo khi xảy ra sự cố hoặc các sự kiện quan trọng.
- **Amazon SES** gửi email xác nhận đặt lịch, nhắc lịch khám và thông báo đến người dùng.

**Bảo mật hệ thống**

- **AWS IAM** quản lý người dùng, vai trò và phân quyền truy cập tài nguyên AWS.
- **AWS Secrets Manager** lưu trữ các thông tin nhạy cảm như Access Key, JWT Secret và các thông số kết nối.
- **AWS KMS** mã hóa dữ liệu nhằm đảm bảo an toàn thông tin trong quá trình lưu trữ và truyền tải.

**Môi trường triển khai**

- Frontend: ReactJS + AWS Amplify.
- Backend: Java Spring Boot chạy trên Amazon EC2.
- Database: Amazon DynamoDB.
- Storage: Amazon S3.
- Domain: Amazon Route 53.
- CDN: Amazon CloudFront.
- Security: AWS WAF, IAM, Secrets Manager và AWS KMS.
- Monitoring: Amazon CloudWatch.
- Notification: Amazon SNS và Amazon SES.

---

### 5. Lộ trình & Mốc triển khai

**Tháng 1**

- Phân tích yêu cầu.
- Thiết kế giao diện.
- Thiết kế cơ sở dữ liệu.
- Thiết kế kiến trúc AWS.

**Tháng 2**

- Phát triển Backend.
- Phát triển Frontend.
- Kết nối DynamoDB.
- Kết nối S3.

**Tháng 3**

- Triển khai hệ thống lên AWS.
- Kiểm thử.
- Tối ưu.
- Hoàn thiện báo cáo.

---

### 6. Ước tính ngân sách

Có thể xem chi phí bằng **AWS Pricing Calculator** để ước tính chi phí triển khai hệ thống.

#### Chi phí hạ tầng

- **Amazon EC2:** 0,30 USD/tháng (01 máy chủ t3.micro chạy Backend Spring Boot trong môi trường thử nghiệm).
- **Application Load Balancer (ALB):** 0,06 USD/tháng (cân bằng tải cho Backend với lưu lượng thấp).
- **Amazon DynamoDB:** 0,08 USD/tháng (lưu trữ dữ liệu người dùng, bác sĩ, dịch vụ và lịch hẹn).
- **Amazon S3:** 0,10 USD/tháng (02 bucket lưu trữ hình ảnh, tài liệu và dữ liệu tĩnh).
- **AWS Amplify:** 0,15 USD/tháng (triển khai và lưu trữ ứng dụng React).
- **Amazon CloudFront:** 0,05 USD/tháng (phân phối nội dung và tăng tốc truy cập).
- **Amazon Route 53:** 0,04 USD/tháng (quản lý tên miền và DNS).
- **AWS WAF:** 0,10 USD/tháng (bảo vệ hệ thống trước các cuộc tấn công phổ biến).
- **Amazon CloudWatch:** 0,05 USD/tháng (theo dõi log, hiệu năng và tài nguyên hệ thống).
- **Amazon SNS:** 0,02 USD/tháng (gửi thông báo khi có sự kiện hoặc cảnh báo).
- **Amazon SES:** 0,04 USD/tháng (gửi email xác nhận đặt lịch và thông báo).
- **AWS Secrets Manager:** 0,03 USD/tháng (quản lý thông tin bảo mật như API Key và Database Secret).
- **AWS KMS:** 0,02 USD/tháng (mã hóa dữ liệu và khóa bảo mật).

#### Tổng chi phí

**Tổng:** **1,04 USD/tháng**, tương đương khoảng **12,48 USD/12 tháng** *(ước tính đối với môi trường demo, quy mô nhỏ và tận dụng AWS Free Tier khi có thể).*

---

### 7. Đánh giá rủi ro

#### Ma trận rủi ro

- EC2 gặp sự cố.
- Người dùng truy cập tăng đột biến.
- Mất kết nối Internet.
- Sai cấu hình AWS.
- Lộ thông tin đăng nhập.

#### Chiến lược giảm thiểu

- Sử dụng CloudWatch để giám sát.
- Sử dụng WAF chống tấn công.
- Lưu Secret bằng Secrets Manager.
- Phân quyền bằng IAM.
- Sao lưu dữ liệu định kỳ.

#### Kế hoạch dự phòng

- Khôi phục dữ liệu từ S3.
- Khởi tạo lại EC2.
- Theo dõi log bằng CloudWatch.
- Gửi cảnh báo qua SNS và Email.

---

### 8. Kết quả kỳ vọng

- Xây dựng thành công hệ thống đặt lịch khám nha khoa trực tuyến.
- Hệ thống hoạt động ổn định trên AWS Cloud.
- Đảm bảo tính bảo mật, khả năng mở rộng và tính sẵn sàng cao.
- Giảm thời gian quản lý lịch khám.
- Tăng trải nghiệm người dùng.
- Làm nền tảng cho việc phát triển thêm các chức năng như thanh toán trực tuyến, chatbot AI và hồ sơ bệnh án điện tử trong tương lai.
