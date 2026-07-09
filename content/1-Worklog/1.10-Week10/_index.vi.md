---
title: "Worklog Tuần 10"
date: 2026-06-2208
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---

### Mục tiêu tuần 10:

- Hoàn thiện upload ảnh sản phẩm và tích hợp thanh toán ZaloPay.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc                                                                                                                                                | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | -------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | -------------- |
| 2   | - Tạo S3 Product Images Bucket riêng để lưu hình ảnh sản phẩm, tách biệt với bucket frontend.                                                            | 22/06/2026   | 22/06/2026      |
| 3   | - Xây dựng API tạo presigned URL để trình duyệt admin có thể upload ảnh trực tiếp lên S3.                                                                | 23/06/2026   | 23/06/2026      |                |
| 4   | - Tích hợp upload ảnh trong trang admin. Kiểm tra upload ảnh, lưu URL ảnh vào sản phẩm và hiển thị ảnh trên website.                                     | 24/06/2026   | 24/06/2026      |                |
| 5   | - Tích hợp ZaloPay Sandbox. Tìm hiểu luồng tạo thanh toán, redirect người dùng và nhận callback.                                                         | 25/06/2026   | 25/06/2026      |                |
| 6   | - Hoàn thiện luồng thanh toán cơ bản. Lambda tạo payment request, ZaloPay callback về API Gateway và Lambda cập nhật trạng thái đơn hàng trong DynamoDB. | 26/06/2026   | 26/06/2026      |                |

### Kết quả đạt được tuần 10:

- Admin upload được ảnh sản phẩm qua S3 presigned URL, hệ thống có luồng thanh toán ZaloPay Sandbox cơ bản.
