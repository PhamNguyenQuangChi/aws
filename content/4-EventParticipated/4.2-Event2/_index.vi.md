---
title: "Event 2"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 4.2. </b> "
---



# Bài Thu Hoạch Chuỗi Hội Thảo Công Nghệ First Cloud Journey

## Mục Đích Của Sự Kiện

**Chia sẻ best practices trong thiết kế ứng dụng hiện đại:** Định hình tư duy Cloud-native, thực hiện chuyển đổi từ quản lý hạ tầng vật lý On-Premise thủ công sang mô hình tự động hóa bằng mã nguồn (IaC - Terraform) và xây dựng văn hóa DevOps.

**Giới thiệu phương pháp DDD và event-driven architecture:** Tiếp cận giải pháp xây dựng kiến trúc thời gian thực thông qua giao thức WebSockets và cơ chế xử lý phi trạng thái (Stateless Lambda), phối hợp phân tách bài toán dữ liệu lớn bằng đồ thị tri thức (Knowledge Graph).

**Hướng dẫn lựa chọn compute services phù hợp:** Phân tích bản chất, ưu nhược điểm kỹ thuật và so sánh chi tiết giữa nền tảng Ảo hóa truyền thống (Virtual Machines) với công nghệ Đóng gói ứng dụng gọn nhẹ (Containerization - Docker).

**Giới thiệu công cụ AI hỗ trợ development lifecycle:** Khai phá sức mạnh của các mô hình ngôn ngữ lớn (LLM) tích hợp với Amazon Bedrock Knowledge Bases và cơ sở dữ liệu đồ thị Amazon Neptune nhằm ứng dụng mô hình GraphRAG tối tân.

---

## Danh Sách Diễn Giả

| Diễn giả | Vai trò |
| --- | --- |
| Vinh Tran | System Administrator at Central Retail Group |
| Bao Huynh | Junior Cloud Native Developer, Endava Vietnam (Founder of ITea Lab) |
| Lê Hoàng Gia Đại | AWS Cloud Engineer & Cyber Security Engineer, Team AWS G3 |
| Nguyen Quoc Bao | Cloud Game Core Developer / WebSocket Specialist |
| Viet Phat | AI Majoring, Swinburne University of Technology |
| Trương Huy Phước | Presenter on Soft Skills & Team Management |

---

## Nội Dung Nổi Bật

### 1. Ảnh hưởng tiêu cực của kiến trúc ứng dụng cũ

* **Thời gian release sản phẩm lâu → Mất doanh thu/bỏ lỡ cơ hội:** Vận hành trên hạ tầng On-Premise truyền thống đòi hỏi cấu hình thủ công phức tạp. Quy trình đóng gói thiếu tính nhất quán dẫn đến lỗi "chạy được trên máy tôi nhưng lỗi trên server", kéo dài chu kỳ phát hành sản phẩm.
* **Hoạt động kém hiệu quả → Mất năng suất, tốn kém chi phí:** Máy chủ ảo hóa truyền thống (VM) bắt buộc mỗi VM phải gánh một hệ điều hành khách (Guest OS) riêng biệt, tiêu tốn CPU, RAM và lưu trữ. Cập nhật bản vá độc lập cho từng VM gây lãng phí tài nguyên và giảm năng suất vận hành.
* **Không tuân thủ quy định bảo mật → Mất an ninh, uy tín:** Chỉ dựa vào giải pháp bảo vệ theo tập luật dấu hiệu (Signature-based) như WAF thông thường không đủ ngăn chặn tấn công tinh vi (SQL Injection nâng cao, XSS, Bot cào dữ liệu). Thiếu giám sát hành vi luồng mạng thời gian thực khiến hệ thống đối mặt rủi ro an ninh lớn.

### 2. Chuyển đổi sang kiến trúc ứng dụng mới – Microservice Architecture

Chuyển từ mô hình đóng gói nguyên khối sang hệ thống modular linh hoạt, mỗi chức năng chạy độc lập trong container, dựa trên 3 trụ cột cốt lõi:

* **Queue Management & State:** Xử lý điều phối dữ liệu kết nối thời gian thực qua API Gateway WebSocket, quản lý phiên làm việc tập trung vào DynamoDB.
* **Caching Strategy:** Áp dụng Docker Layer Caching trong quá trình build Dockerfile, giúp giảm thời gian build và tối ưu CI/CD.
* **Message Handling:** Thiết lập giao tiếp hai chiều toàn song công (Full-duplex) qua WebSocket bền vững, cho phép AWS Lambda đẩy dữ liệu trạng thái đến nhiều client cùng lúc.

### 3. Domain-Driven Design (DDD) và Phân ranh giới Hệ thống

* **Phương pháp phân tách và xử lý dữ liệu:** Chunking, Entity extraction và Embeddings generation để xác lập ranh giới tri thức.
* **Case study liên kết thực thể:** Multi-hop Reasoning thông qua duyệt đồ thị, liên kết thực thể giữa nhiều tài liệu để loại bỏ hiện tượng ảo giác (hallucination) của AI.
* **Context mapping:** Sơ đồ ngữ cảnh dữ liệu qua các Node (thực thể) và Edge (mối quan hệ) trong Amazon Neptune Analytics.

### 4. Event-Driven Architecture (Kiến trúc hướng sự kiện)

* **3 patterns tích hợp:** HTTP Polling (Login/Leaderboard), UDP/ENet (FPS/Đua xe cần độ trễ thấp), WebSockets (Turn-based game, Chat, Lobby).
* **Lợi ích:** Tính độc lập cao giữa Client và Server, tự động cập nhật trạng thái đồng bộ khi có sự kiện mới.
* **So sánh sync vs async:** Đánh đổi kỹ thuật khi dùng Stateless Lambda — do không giữ dữ liệu giữa các request, hệ thống phải liên tục đọc/ghi trạng thái từ DynamoDB.

### 5. Compute Evolution (Sự tiến hóa của hạ tầng tính toán)

* **Shared Responsibility Model:** On-Premise → VM (Guest OS riêng) → Docker Container (chia sẻ Host OS Kernel) → AWS Lambda (Serverless).
* **Serverless & Container benefits:** Đóng gói mã nguồn cùng dependencies để chạy đồng nhất mọi môi trường (Build once, run anywhere).
* **Functions vs Containers:** Docker Container cho Microservices dài hạn, ổn định; AWS Lambda cho tác vụ ngắn hạn theo sự kiện để tối ưu chi phí.

### 6. Amazon Q Developer và Hệ sinh thái Cloud hỗ trợ phát triển

* **SDLC automation:** Terraform (IaC) tự động hóa cấu hình, khởi tạo tài nguyên và quản lý phiên bản triển khai.
* **Code & Database transformation:** Thuật toán tối ưu ML xử lý mất cân bằng dữ liệu, dashboard giám sát tấn công mạng thời gian thực.
* **AWS Transform agents / Managed Services:** Fully Managed Route (Bedrock Knowledge Bases + Neptune Analytics) và Custom Route (LlamaIndex + Neptune qua Cypher Query).

---

## Những Gì Học Được

### Tư Duy Thiết Kế

* **Business-first approach:** Mọi giải pháp công nghệ phải xuất phát từ mục tiêu rõ ràng, thống nhất của tổ chức.
* **Ubiquitous language:** Truyền thông cởi mở, lắng nghe chủ động để thiết lập tiếng nói chung, gạt bỏ rào cản thông tin.
* **Bounded contexts:** "Đúng người, đúng việc" đi cùng tinh thần trách nhiệm cá nhân, phân định rõ ranh giới công việc.

### Kiến Trúc Kỹ Thuật

* **Mô hình hóa quy trình thời gian thực:** Ánh xạ luồng dữ liệu từ Client (Godot) lên Cloud qua Route Key của API Gateway.
* **Event-driven:** Thay HTTP Polling bằng WebSocket bền vững, tối ưu băng thông và trải nghiệm real-time.
* **Integration patterns:** Kết hợp AWS WAF (tầng ứng dụng web) với NIDS dựa trên ML (giám sát hành vi mạng) trên tập dữ liệu CSE-CIC-IDS2018.
* **Compute spectrum:** Phân biệt VM (cô lập phần cứng, OS riêng) và Docker Container (cô lập ứng dụng, chia sẻ OS).

### Chiến Lược Hiện Đại Hóa

* **Phased approach:** Lộ trình từ IT Helpdesk → mạng, Linux → Cloud/DevOps; tập trung xây Portfolio thực tế thay vì chạy theo chứng chỉ.
* **Framework hiện đại hóa ứng dụng:** Chuyển mã nguồn sang Docker Container để đồng bộ trong CI/CD, giải quyết xung đột môi trường.
* **ROI measurement:** Dùng công cụ số hóa (Trello, ClickUp, Google Workspace, Slack, Discord) để đo hiệu suất nhóm.

---

## Ứng Dụng Vào Công Việc

* **Áp dụng mô hình làm việc nhóm:** Thực thi 4 quy tắc vàng của Teamwork, phân chia công việc trên Trello/ClickUp.
* **Refactor và đóng gói mã nguồn:** Viết Dockerfile chuẩn hóa, tận dụng cache layer để tăng tốc đóng gói khi bàn giao.
* **Implement event-driven patterns:** Thử nghiệm tính năng real-time (chat nội bộ, thông báo) qua WebSocket + API Gateway.
* **Ứng dụng Serverless:** Tách logic xử lý ngắn hạn sang AWS Lambda, lưu phiên làm việc vào DynamoDB để tối ưu chi phí.
* **Nghiên cứu bảo mật và AI nâng cao:** Tích hợp GenAI qua Bedrock để nâng cấp NIDS; nghiên cứu GraphRAG cho hệ thống tìm kiếm tri thức doanh nghiệp.

---

## Trải Nghiệm Trong Event

Tham gia chuỗi hội thảo First Cloud Journey là trải nghiệm học tập thực tiễn cao, bao quát từ lộ trình phát triển bản thân, kỹ thuật hạ tầng, tư duy bảo mật, giải pháp AI thế hệ mới đến kỹ năng làm việc nhóm.

### Học hỏi từ các diễn giả có chuyên môn cao

* Diễn giả Vinh Trần chia sẻ hành trình từ IT Helpdesk lên Senior Sysadmin tại Central Retail Group, minh chứng cho năng lực tự học thực chiến.
* Các chuyên gia trẻ (Bảo Huỳnh, Gia Đại, Quốc Bảo, Việt Phát) mang đến kiến thức chuyên sâu về Cloud-native, AI và An ninh mạng từ thực tế triển khai.

### Trải nghiệm kỹ thuật thực tế

* Tiếp cận cấu trúc viết Dockerfile chuẩn, hiểu rõ ảnh hưởng của layer đến tốc độ build và tài nguyên hệ thống.
* Quan sát kiến trúc game multiplayer thời gian thực qua demo Godot client kết nối với DynamoDB.
* Nhận thức tầm quan trọng của tối ưu ML khi xử lý mất cân bằng dữ liệu trong phát hiện tấn công mạng.

### Ứng dụng công cụ hiện đại

* Khám phá hệ sinh thái AWS: WAF, Lambda, Neptune, Bedrock.
* Tiếp cận tư duy quản trị dự án qua Slack, Discord, Trello cho làm việc nhóm từ xa.

### Kết nối và trao đổi

* Thảo luận các bài học thực tế (lỗi Stale connections - GoneException, chi phí Scan dữ liệu lớn trong DynamoDB).
* Nhận ra triết lý: kỹ thuật tối tân vẫn cần sự phối hợp nhịp nhàng và quy trình làm việc nhóm cởi mở.

---

## Bài Học Rút Ra

1. **"Never test in production"** — Bảo vệ tính sẵn sàng của hệ thống là bảo vệ uy tín và thời gian của cả đội ngũ.
2. Giải pháp bảo mật dựa trên chữ ký (Signature-based) không đủ trước mối đe dọa hiện đại; cần kết hợp giám sát hành vi bằng ML.
3. Hiện đại hóa ứng dụng qua mô hình đồ thị tri thức (GraphRAG) giải quyết hạn chế liên kết tài liệu đa bước của RAG truyền thống.
![Buổi event](/images/4-Event/event2.jpg)
---


## Tổng Kết Luận

Tổng thể, sự kiện không chỉ cung cấp những khối kiến thức kỹ thuật chuyên sâu, thực tế từ Docker, WebSockets, Học máy cho đến GraphRAG mà còn mang lại bài học vô giá về tư duy phát triển sự nghiệp bền bỉ và nghệ thuật phối hợp làm việc nhóm hiệu quả cao trong mọi dự án.