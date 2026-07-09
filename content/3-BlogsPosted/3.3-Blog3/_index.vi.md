---
title: "Blog 3"
date: 2026-07-05
weight: 3
chapter: false
pre: " <b> 3.3. </b> "
---

# BIẾN AMAZON CLOUDWATCH THÀNH LỚP GIÁM SÁT CHỦ ĐỘNG CHO HỆ THỐNG

Trong quá trình tìm hiểu về vận hành hệ thống trên AWS, em nhận ra rằng Amazon CloudWatch không chỉ là công cụ để xem CPU hoặc nhận email khi server quá tải. Nếu biết cách kết hợp **Metrics, Logs, Dashboards và Alarms**, CloudWatch có thể trở thành trung tâm giám sát giúp phát hiện sự cố sớm và hỗ trợ phản ứng tự động.

Một hệ thống monitoring tốt không chỉ cho biết hệ thống đã lỗi, mà còn giúp phát hiện dấu hiệu bất thường trước khi người dùng bị ảnh hưởng.

## 1. Amazon CloudWatch thực sự làm gì?

Amazon CloudWatch là dịch vụ **Monitoring & Observability** của AWS. CloudWatch có nhiệm vụ thu thập dữ liệu từ các tài nguyên như EC2, RDS, Lambda, ECS, API Gateway và nhiều dịch vụ khác.

CloudWatch giúp trả lời ba câu hỏi quan trọng:

- Hệ thống đang hoạt động như thế nào?
- Có lỗi hoặc dấu hiệu bất thường nào đang xảy ra không?
- Nếu có lỗi, cần thông báo hoặc xử lý tự động như thế nào?

Vì vậy, CloudWatch không chỉ là nơi xem biểu đồ. Nó là một thành phần quan trọng trong vận hành hệ thống cloud.

<img src="/workshop-/images/3-BlogsPosted/blog3-cloudwatch-monitoring.png" alt="Amazon CloudWatch Monitoring Architecture" style="max-width: 100%; height: auto;">

## 2. Không nên chỉ nhìn CPU

Một sai lầm phổ biến khi cấu hình monitoring là chỉ tạo alarm cho CPU, ví dụ CPU vượt quá 80%.

Tuy nhiên, CPU chỉ phản ánh một phần tình trạng hệ thống. Một dashboard hiệu quả nên theo dõi nhiều chỉ số cùng lúc, ví dụ:

- CPU Utilization.
- Memory Usage.
- Disk Space.
- Network In/Out.
- Request Count.
- Error Rate.
- Response Time hoặc Latency.

Khi đặt các metrics cạnh nhau, người vận hành có thể dễ dàng phân tích nguyên nhân gốc thay vì chỉ biết rằng hệ thống đang chậm.

Ví dụ, nếu latency tăng nhưng CPU không cao, nguyên nhân có thể không nằm ở compute mà có thể đến từ database, network hoặc external API.

## 3. Logs là nơi giải thích nguyên nhân

Metrics cho biết điều gì đang xảy ra, còn Logs giúp giải thích vì sao điều đó xảy ra.

Ví dụ:

- API Error Rate tăng.
- Dashboard hiển thị latency tăng đột biến.
- CloudWatch Logs cho thấy nguyên nhân là truy vấn database bị timeout.

Việc gom log từ Lambda, API Gateway, EC2 hoặc ứng dụng về CloudWatch giúp quá trình debug nhanh hơn nhiều so với việc kiểm tra từng máy hoặc từng service riêng lẻ.

Trong kiến trúc serverless, CloudWatch Logs đặc biệt quan trọng vì Lambda không có server cố định để SSH vào kiểm tra. Mọi thông tin debug gần như đều phải dựa vào logs.

## 4. Alarm không chỉ để gửi email

CloudWatch Alarm không chỉ dùng để gửi email thông báo lỗi. Một alarm tốt có thể kích hoạt nhiều hành động tự động như:

- Gửi email qua Amazon SNS.
- Kích hoạt Auto Scaling.
- Gọi AWS Lambda để xử lý sự cố.
- Kích hoạt Systems Manager Automation.
- Thông báo cho đội vận hành hoặc DevOps.

Điều này giúp hệ thống phản ứng trong vài giây thay vì chờ quản trị viên kiểm tra thủ công.

## 5. Ví dụ thực tế

Giả sử một website thương mại điện tử chuẩn bị bước vào đợt Flash Sale. Lượng truy cập tăng gấp nhiều lần so với ngày thường.

CloudWatch có thể phát hiện:

- CPU vượt ngưỡng.
- Request latency tăng.
- Error rate bắt đầu xuất hiện.
- API Gateway có nhiều lỗi 5xx.
- Lambda duration tăng bất thường.

Khi đó, CloudWatch Alarm có thể được kích hoạt. Alarm gửi thông báo đến Amazon SNS, sau đó SNS gửi email cảnh báo cho đội vận hành.

Nếu hệ thống có cấu hình phản ứng tự động, alarm cũng có thể kích hoạt Lambda hoặc Systems Manager để thực hiện một số hành động khắc phục.

Nếu không có monitoring tốt, nhiều khả năng người dùng sẽ là người đầu tiên phát hiện website gặp sự cố.

## 6. Ứng dụng vào dự án ecommerce của em

Trong dự án AWS Serverless E-commerce Platform, CloudWatch có thể được sử dụng để theo dõi các thành phần chính như:

- API Gateway request count.
- API Gateway 4xx và 5xx errors.
- Lambda errors.
- Lambda duration.
- Lambda throttles.
- EventBridge scheduled job execution.
- Logs của EcommerceBackendFunction.
- Logs của PaymentExpirySchedulerFunction.
- Logs của RefundReconciliationFunction.

Khi có lỗi, CloudWatch Alarm có thể gửi cảnh báo đến Amazon SNS. SNS sau đó gửi email cho admin hoặc người vận hành hệ thống.

Luồng monitoring trong dự án:

```text
API Gateway / Lambda / EventBridge
   ↓
Amazon CloudWatch Logs & Metrics
   ↓
CloudWatch Alarm
   ↓
Amazon SNS
   ↓
Alert Email
```

## 7. Điều em học được

Sau khi tìm hiểu CloudWatch, em rút ra một số điểm quan trọng.

Thứ nhất, monitoring không chỉ là xem biểu đồ CPU. Một hệ thống cần theo dõi nhiều metrics khác nhau để đánh giá đúng tình trạng hoạt động.

Thứ hai, logs đóng vai trò rất quan trọng trong việc tìm nguyên nhân lỗi, đặc biệt với các hệ thống serverless như Lambda.

Thứ ba, alarm nên được thiết kế để hỗ trợ phản ứng nhanh, không chỉ gửi thông báo mà còn có thể kích hoạt các hành động tự động.

Thứ tư, CloudWatch là một phần quan trọng trong vận hành hệ thống production vì giúp phát hiện sớm sự cố và giảm thời gian xử lý lỗi.

## 8. Kết luận

Amazon CloudWatch không chỉ là công cụ xem CPU hoặc gửi email cảnh báo cơ bản. Khi kết hợp Metrics, Logs, Dashboards và Alarms, CloudWatch có thể trở thành một lớp giám sát chủ động cho hệ thống.

Monitoring hiệu quả không phải là biết hệ thống đã lỗi, mà là phát hiện và xử lý vấn đề trước khi người dùng bị ảnh hưởng.

Thông qua bài viết này, em hiểu rõ hơn vai trò của CloudWatch trong vận hành hệ thống AWS và cách áp dụng CloudWatch vào dự án ecommerce serverless của mình.

## 9. Tài liệu tham khảo

- Amazon CloudWatch Documentation
- Amazon CloudWatch Logs Documentation
- Amazon CloudWatch Alarms Documentation
- Amazon SNS Documentation
- AWS Lambda Monitoring Documentation
- Amazon API Gateway Monitoring Documentation
