---
title: "Worklog Tuần 4"
date: 2026-05-11
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

### Mục tiêu tuần 4:

- Phân tích yêu cầu và thiết kế kiến trúc tổng thể cho dự án ecommerce.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc                                                                                                                                                         | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | -------------- |
| 2   | - Xác định đề tài dự án là Mimi Jewelry E-commerce Project. Liệt kê các chức năng chính như xem sản phẩm, giỏ hàng, checkout, thanh toán và quản lý admin.        | 11/05/2026   | 11/05/2026      |
| 3   | - Thiết kế kiến trúc tổng thể gồm Frontend Layer, Authentication Layer, API Layer, Compute Layer, Data Layer, Integration Layer, Monitoring Layer và CI/CD Layer. | 12/05/2026   | 12/05/2026      |                |
| 4   | - Thiết kế luồng người dùng: truy cập CloudFront, tải frontend từ S3, đăng nhập bằng Cognito, gọi API Gateway, Lambda xử lý và DynamoDB lưu dữ liệu.              | 13/05/2026   | 13/05/2026      |                |
| 5   | - Thiết kế luồng admin: đăng nhập, quản lý sản phẩm, upload ảnh sản phẩm, quản lý đơn hàng và xử lý trạng thái thanh toán.                                        | 14/05/2026   | 15/05/2026      |                |
| 6   | - Hoàn thiện sơ đồ kiến trúc ban đầu. Xác định dự án không dùng EC2, ECS, RDS hay Application Load Balancer mà dùng kiến trúc serverless.                         | 15/05/2026   | 15/05/2026      |                |

### Kết quả đạt được tuần 4:

- Có kiến trúc tổng thể rõ ràng và danh sách các dịch vụ AWS sẽ sử dụng trong dự án.
