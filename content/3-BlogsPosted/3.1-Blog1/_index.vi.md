---
title: "Blog 1"
date: 2026-07-08
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---

# TỰ ĐỘNG HÓA PHẢN ỨNG SỰ CỐ BẢO MẬT TRÊN AWS

Trong quá trình tìm hiểu về các dịch vụ bảo mật trên AWS, em đã đọc bài viết **"How to get started with security response automation on AWS"** trên AWS Security Blog.

Điều em ấn tượng nhất là cách AWS xây dựng một quy trình tự động phát hiện và xử lý các sự cố bảo mật theo mô hình **event-driven architecture**. Thay vì đội ngũ vận hành phải theo dõi cảnh báo và xử lý thủ công, AWS có thể kết hợp nhiều dịch vụ như **AWS CloudTrail, Amazon EventBridge, AWS Lambda, AWS Systems Manager và Amazon SNS** để tạo thành một pipeline phản ứng sự cố tự động.

Kiến trúc này giúp hệ thống phát hiện nhanh các sự kiện bất thường, tự động thực hiện hành động khắc phục và gửi thông báo đến đội ngũ vận hành.

## 1. Bài toán đặt ra

Trong một hệ thống AWS, có nhiều sự kiện có thể gây rủi ro bảo mật nếu không được xử lý kịp thời, ví dụ:

- AWS CloudTrail bị tắt.
- Security Group mở toàn bộ Internet.
- Amazon S3 Bucket bị public.
- IAM Access Key được tạo hoặc sử dụng bất thường.
- EC2 instance có dấu hiệu bị tấn công.
- Security Hub hoặc GuardDuty phát hiện finding nghiêm trọng.

Theo cách làm truyền thống, đội ngũ Security hoặc DevOps phải nhận cảnh báo, kiểm tra nguyên nhân, xác định mức độ ảnh hưởng rồi mới thực hiện các bước khắc phục. Quy trình này tốn thời gian và phụ thuộc nhiều vào con người.

AWS đề xuất tự động hóa quy trình phản ứng để hệ thống có thể xử lý ngay khi sự kiện xảy ra.

## 2. Kiến trúc tổng thể

Theo cách em hiểu, quy trình tự động hóa phản ứng sự cố bảo mật hoạt động như sau:

```text
Security Event
   ↓
CloudTrail / GuardDuty / AWS Config
   ↓
Amazon EventBridge
   ↓
AWS Lambda
   ↓
AWS Systems Manager Automation
   ↓
Remediation + SNS Notification
```

Điểm nổi bật của kiến trúc này là hệ thống chỉ được kích hoạt khi có sự kiện bảo mật xảy ra. Nhờ đó, tài nguyên được sử dụng hiệu quả hơn và thời gian phản ứng cũng nhanh hơn nhiều so với xử lý thủ công.

<img src="/workshop-/images/3-BlogsPosted/blog1-security-response.png" alt="Security Response Automation Architecture" style="max-width: 100%; height: auto;">

## 3. Vai trò của từng dịch vụ

### AWS CloudTrail

AWS CloudTrail ghi lại toàn bộ hoạt động API trong tài khoản AWS. Đây là nguồn dữ liệu quan trọng để phát hiện các hành động bất thường như tắt logging, tạo access key mới, thay đổi security group hoặc public S3 bucket.

### Amazon EventBridge

Amazon EventBridge đóng vai trò lắng nghe sự kiện. Khi CloudTrail, AWS Config, GuardDuty hoặc Security Hub phát sinh sự kiện phù hợp với rule đã cấu hình, EventBridge sẽ tự động kích hoạt bước xử lý tiếp theo.

### AWS Lambda

AWS Lambda được dùng để thực hiện các hành động khắc phục tự động. Ví dụ:

- Bật lại CloudTrail nếu bị tắt.
- Cập nhật Security Group để đóng port public.
- Thu hồi hoặc vô hiệu hóa IAM Access Key bất thường.
- Gọi Systems Manager Automation để xử lý workflow phức tạp.

### AWS Systems Manager

AWS Systems Manager được sử dụng khi cần xử lý các workflow nhiều bước, ví dụ như cách ly EC2 instance, chạy automation document hoặc thực hiện remediation theo kịch bản đã định nghĩa.

### Amazon SNS

Sau khi xử lý xong, Amazon SNS gửi thông báo đến đội ngũ vận hành hoặc bảo mật để họ có thể kiểm tra và theo dõi kết quả xử lý.

## 4. Luồng hoạt động

Luồng xử lý có thể được mô tả như sau:

1. Một sự kiện bảo mật xảy ra trong tài khoản AWS.
2. CloudTrail hoặc dịch vụ bảo mật khác ghi nhận sự kiện.
3. EventBridge phát hiện sự kiện phù hợp với rule đã cấu hình.
4. EventBridge kích hoạt Lambda.
5. Lambda thực hiện remediation hoặc gọi Systems Manager Automation.
6. SNS gửi thông báo đến đội ngũ vận hành.
7. CloudWatch Logs ghi lại quá trình xử lý để phục vụ kiểm tra sau này.

Toàn bộ quy trình có thể hoàn thành trong thời gian ngắn mà không cần thao tác thủ công.

## 5. Điều em học được

Sau khi tìm hiểu bài viết, em rút ra một số điểm quan trọng.

Thứ nhất, việc phát hiện sự cố thôi là chưa đủ. Một hệ thống bảo mật tốt cần có khả năng phản ứng nhanh và tự động hóa các bước xử lý lặp lại.

Thứ hai, kiến trúc event-driven rất phù hợp cho các bài toán bảo mật vì hệ thống chỉ hoạt động khi có sự kiện phát sinh. Điều này giúp tối ưu chi phí và dễ mở rộng.

Thứ ba, việc kết hợp CloudTrail, EventBridge, Lambda, Systems Manager và SNS giúp tạo ra một pipeline bảo mật linh hoạt, có thể áp dụng cho nhiều tình huống khác nhau như:

- Khắc phục S3 Bucket public.
- Đóng Security Group mở Internet.
- Thu hồi IAM Access Key bất thường.
- Cách ly EC2 instance nghi ngờ bị tấn công.
- Xử lý Security Hub Findings.

## 6. Kết luận

Thông qua bài blog này, em hiểu rõ hơn cách AWS xây dựng hệ thống **Security Response Automation** bằng cách kết hợp nhiều dịch vụ serverless và managed services.

Điều em đánh giá cao nhất là khả năng tự động phát hiện và phản ứng gần như theo thời gian thực. Điều này giúp giảm sự phụ thuộc vào thao tác thủ công, rút ngắn thời gian xử lý sự cố và nâng cao hiệu quả vận hành bảo mật.

Trong thời gian tới, em muốn thử triển khai lại kiến trúc này để hiểu rõ hơn cách các dịch vụ AWS phối hợp với nhau trong một hệ thống bảo mật thực tế.

## 7. Tài liệu tham khảo

- AWS Security Blog: How to get started with security response automation on AWS
- AWS CloudTrail Documentation
- Amazon EventBridge Documentation
- AWS Lambda Documentation
- AWS Systems Manager Documentation
- Amazon SNS Documentation
