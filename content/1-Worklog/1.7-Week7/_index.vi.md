---
title: "Worklog Tuần 7"
date: 2026-06-01
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Mục tiêu tuần 7:

- Thiết kế database và tích hợp DynamoDB vào backend.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc                                                                                                                            | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | ------------------------------------------------------------------------------------------------------------------------------------ | ------------ | --------------- | -------------- |
| 2   | - Thiết kế bảng Products trong DynamoDB để lưu tên sản phẩm, mô tả, giá, hình ảnh, tồn kho và trạng thái hiển thị.                   | 01/06/2026   | 01/06/2026      |
| 3   | - Thiết kế bảng Orders để lưu thông tin đơn hàng, khách hàng, sản phẩm đã mua, tổng tiền, trạng thái thanh toán và trạng thái xử lý. | 02/06/2026   | 02/06/2026      |                |
| 4   | - Tích hợp Lambda với DynamoDB cho nhóm API sản phẩm, thay dữ liệu mẫu bằng dữ liệu thật từ DynamoDB.                                | 03/06/2026   | 03/06/2026      |                |
| 5   | - Tích hợp Lambda với DynamoDB cho nhóm API đơn hàng, xử lý tạo đơn hàng, cập nhật trạng thái và thay đổi tồn kho.                   | 04/06/2026   | 04/06/2026      |                |
| 6   | - Kiểm tra luồng dữ liệu giữa frontend, API Gateway, Lambda và DynamoDB. Sửa lỗi IAM permission, format dữ liệu và truy vấn.         | 05/06/2026   | 05/06/2026      |                |

### Kết quả đạt được tuần 7:

- DynamoDB hoạt động với Products và Orders, backend có thể đọc/ghi dữ liệu thật trên AWS.
