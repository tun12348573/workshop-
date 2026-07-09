---
title: "Worklog Tuần 11"
date: 2026-06-29
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---

### Mục tiêu tuần 11:

- Xây dựng tác vụ nền, monitoring và alert cho hệ thống.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc                                                                                                                                 | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | ----------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | -------------- |
| 2   | - Xây dựng PaymentExpirySchedulerFunction để kiểm tra các đơn hàng chờ thanh toán quá hạn và cập nhật trạng thái đơn hàng.                | 29/06/2026   | 29/06/2026      |
| 3   | - Cấu hình EventBridge để trigger PaymentExpirySchedulerFunction theo lịch. Kiểm tra Lambda chạy tự động không cần request từ người dùng. | 30/06/2026   | 30/06/2026      |                |
| 4   | - Xây dựng RefundReconciliationFunction để đối soát trạng thái hoàn tiền với ZaloPay và cập nhật dữ liệu liên quan.                       | 01/07/2026   | 01/07/2026      |                |
| 5   | - Cấu hình CloudWatch Logs và Metrics cho Lambda, API Gateway và các function chạy nền. Kiểm tra log để debug lỗi.                        | 02/07/2026   | 02/07/2026      |                |
| 6   | - Cấu hình CloudWatch Alarm và SNS Topic. Xác nhận email subscription để nhận cảnh báo khi hệ thống có lỗi.                               | 03/07/2026   | 03/07/2026      |                |

### Kết quả đạt được tuần 11:

- Hệ thống có scheduled jobs, log, monitoring và cảnh báo email phục vụ vận hành.
