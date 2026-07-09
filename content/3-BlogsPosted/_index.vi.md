---
title: "Các bài blogs đã đăng"
date: 2026-04-17
weight: 3
chapter: false
pre: " <b> 3. </b> "
---

### [Blog 1 - Tự động hóa phản ứng sự cố bảo mật trên AWS](3.1-Blog1/)

Bài blog này tóm tắt những gì em đã học được từ bài viết trên AWS Security Blog về tự động hóa phản ứng sự cố bảo mật trên AWS. Nội dung chính giải thích cách các dịch vụ như AWS CloudTrail, Amazon EventBridge, AWS Lambda, AWS Systems Manager và Amazon SNS có thể kết hợp với nhau để tự động phát hiện và xử lý các sự kiện bảo mật. Thông qua bài viết này, em hiểu rõ hơn cách kiến trúc event-driven giúp giảm thao tác thủ công, rút ngắn thời gian phản ứng và nâng cao hiệu quả vận hành bảo mật trên AWS.

### [Blog 2 - Tự động giải nén file trên Amazon S3 bằng AWS Batch và Amazon ECS](3.2-Blog2/)

Bài blog này giới thiệu kiến trúc tự động xử lý và giải nén các file nén được upload lên Amazon S3. Giải pháp sử dụng Amazon S3, Amazon EventBridge, AWS Batch, Amazon ECS và Amazon EBS để xử lý các file TAR dung lượng lớn mà không cần duy trì một server chạy liên tục. Thông qua bài viết này, em hiểu được vì sao AWS Batch phù hợp hơn AWS Lambda đối với các workload xử lý file lớn, đồng thời thấy được lợi ích của việc dùng containerized batch jobs để tối ưu chi phí, khả năng mở rộng và giảm công sức quản lý hạ tầng.

### [Blog 3 - Biến Amazon CloudWatch thành lớp giám sát chủ động cho hệ thống](3.3-Blog3/)

Bài blog này trình bày cách sử dụng Amazon CloudWatch không chỉ như một công cụ xem CPU hoặc gửi cảnh báo cơ bản, mà còn như một lớp giám sát chủ động cho hệ thống. Nội dung bài viết giải thích cách kết hợp Metrics, Logs, Dashboards và Alarms để theo dõi tình trạng hệ thống, phát hiện lỗi sớm và kích hoạt các hành động phản ứng tự động. Thông qua bài viết này, em hiểu rằng monitoring hiệu quả không chỉ là biết hệ thống đã gặp lỗi, mà còn là phát hiện và xử lý vấn đề trước khi người dùng bị ảnh hưởng.
