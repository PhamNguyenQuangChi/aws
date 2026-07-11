---
title: "Blog 2"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 3.2. </b> "
---

# AWS WAF: LÁ CHẮN BẢO VỆ ỨNG DỤNG WEB KHỎI NHỮNG CUỘC TẤN CÔNG PHỔ BIẾN

Khi triển khai một website hoặc ứng dụng lên môi trường Internet, nhiều người thường tập trung vào việc tối ưu hiệu năng, mở rộng hệ thống hoặc cải thiện trải nghiệm người dùng.

Tuy nhiên, một yếu tố quan trọng không kém chính là bảo mật.

Trong thực tế, các ứng dụng web luôn phải đối mặt với nhiều nguy cơ như SQL Injection, Cross-Site Scripting (XSS), Bot Traffic hoặc các cuộc tấn công từ chối dịch vụ (DDoS). Nếu không được bảo vệ đúng cách, những cuộc tấn công này có thể gây gián đoạn dịch vụ, ảnh hưởng đến dữ liệu và làm giảm trải nghiệm của người dùng.

Để giải quyết bài toán này, AWS cung cấp dịch vụ AWS WAF (Web Application Firewall), giúp bảo vệ ứng dụng web khỏi các mối đe dọa phổ biến, đồng thời cho phép quản lý và xây dựng các chính sách bảo mật một cách linh hoạt.

Trong thực tế, AWS WAF thường được triển khai cùng với Application Load Balancer (ALB), Amazon CloudFront, API Gateway và AWS Shield để xây dựng một hệ thống bảo mật nhiều lớp cho ứng dụng.

NHỮNG ĐIỂM NỔI BẬT:
<br>&emsp;• Bảo vệ ứng dụng khỏi các cuộc tấn công phổ biến:
<br>&emsp;AWS WAF có khả năng phát hiện và ngăn chặn nhiều hình thức tấn công thường gặp như SQL Injection, Cross-Site Scripting (XSS), Local File Inclusion và các request độc hại khác trước khi chúng đến ứng dụng.
<br>&emsp;• Tạo luật bảo mật tùy chỉnh:
<br>&emsp;Người dùng có thể xây dựng các rule tùy chỉnh dựa trên địa chỉ IP, quốc gia, header HTTP, URI hoặc nhiều điều kiện khác nhằm đáp ứng yêu cầu bảo mật riêng của từng hệ thống.
<br>&emsp;• Tích hợp với nhiều dịch vụ AWS:
<br>&emsp;AWS WAF có thể hoạt động cùng với Amazon CloudFront, Application Load Balancer (ALB), Amazon API Gateway và AWS AppSync để bảo vệ website, ứng dụng web và API.
<br>&emsp;• Kết hợp với AWS Shield để chống DDoS:
<br>&emsp;Khi được triển khai cùng AWS Shield, hệ thống có thể giảm thiểu tác động của các cuộc tấn công DDoS quy mô lớn. AWS Shield chịu trách nhiệm bảo vệ ở tầng mạng, trong khi AWS WAF sẽ kiểm tra và chặn các request độc hại ở tầng ứng dụng.
<br>&emsp;• Theo dõi và phân tích lưu lượng:
<br>&emsp;AWS WAF có thể tích hợp với Amazon CloudWatch để thu thập log, theo dõi lưu lượng truy cập, phát hiện hành vi bất thường và hỗ trợ quản trị viên đưa ra các phương án xử lý phù hợp.

TÌNH HUỐNG THỰC TẾ:
Giả sử một website thương mại điện tử đang triển khai chương trình khuyến mãi lớn và có hàng nghìn người dùng truy cập cùng lúc.

Trong thời điểm này, kẻ tấn công có thể gửi hàng loạt request chứa mã SQL độc hại hoặc thực hiện các cuộc tấn công DDoS nhằm làm gián đoạn hệ thống.

Kiến trúc triển khai như sau:
User → AWS WAF → Application Load Balancer → EC2 Auto Scaling → Application Web Servers

Trong kiến trúc này:
<br>&emsp;+ AWS WAF sẽ kiểm tra toàn bộ request gửi đến hệ thống.
<br>&emsp;+ Những request chứa mã độc hoặc có dấu hiệu bất thường sẽ bị chặn ngay tại lớp WAF.
<br>&emsp;+ Application Load Balancer phân phối lưu lượng hợp lệ đến các máy chủ ứng dụng.
<br>&emsp;+ Auto Scaling tự động mở rộng số lượng EC2 khi lưu lượng tăng cao.
<br>&emsp;+ CloudWatch ghi nhận log và giám sát toàn bộ hoạt động của hệ thống.
Nhờ đó, ứng dụng vẫn duy trì được tính sẵn sàng cao, đồng thời bảo vệ dữ liệu người dùng khỏi các cuộc tấn công phổ biến.

KẾT LUẬN:
Điều mình thấy ấn tượng ở AWS WAF là dịch vụ này không chỉ hoạt động như một tường lửa ứng dụng web thông thường mà còn có thể kết hợp với nhiều dịch vụ AWS khác để xây dựng một hệ thống bảo mật toàn diện.

Trong kiến trúc sử dụng AWS WAF kết hợp với Application Load Balancer và EC2 Auto Scaling, AWS WAF đóng vai trò là lớp bảo vệ đầu tiên, giúp kiểm tra và lọc toàn bộ request trước khi chúng đi vào hệ thống backend.

Khi kết hợp thêm với AWS Shield, CloudFront và CloudWatch, hệ thống có thể vừa chống lại các cuộc tấn công DDoS, vừa phát hiện và ngăn chặn các hành vi tấn công ở tầng ứng dụng.

Theo mình, đây là một dịch vụ rất đáng tìm hiểu khi học AWS vì nó liên quan trực tiếp đến các lĩnh vực quan trọng như Security, Networking, High Availability và Cloud Architecture.

Thông qua bài này, mình hiểu rõ hơn rằng bảo mật cần được triển khai ngay từ đầu thay vì chỉ xử lý khi sự cố xảy ra. Một hệ thống tốt không chỉ cần hoạt động ổn định mà còn phải đảm bảo an toàn cho dữ liệu và người dùng.

Link tài liệu:

https://docs.aws.amazon.com/.../develope.../waf-chapter.html

https://docs.aws.amazon.com/.../aws-waf-and-shield.html

![Ảnh](/images/3-BlogsPosted/Blog2.jpg)