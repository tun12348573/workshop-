---
title: "Worklog Tuần 8"
date: 2026-06-06
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Mục tiêu tuần 8:

- Tích hợp đăng nhập và phân quyền bằng Amazon Cognito.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc                                                                                                                        | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | -------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | -------------- |
| 2   | - Cấu hình Cognito Customer User Pool để phục vụ khách hàng đăng nhập, đặt hàng và xem lịch sử đơn hàng.                         | 08/06/2026   | 08/06/2026      |
| 3   | - Cấu hình Cognito Admin User Pool để phục vụ admin đăng nhập và quản lý hệ thống.                                               | 09/06/2026   | 09/06/2026      |                |
| 4   | - Tích hợp đăng nhập Cognito vào frontend. Sau khi đăng nhập, frontend nhận JWT token và lưu token để gọi API.                   | 10/06/2026   | 10/06/2026      |                |
| 5   | - Bảo vệ các API quan trọng bằng token. Phân biệt luồng customer và admin, xử lý trường hợp thiếu token hoặc token không hợp lệ. | 11/06/2026   | 11/06/2026      |                |
| 6   | - Test đăng nhập customer và admin. Kiểm tra customer có thể đặt hàng, admin có thể quản lý sản phẩm và đơn hàng.                | 12/06/2026   | 12/06/2026      |                |

### Kết quả đạt được tuần 8:

- Hệ thống có authentication và phân quyền cơ bản giữa customer và admin.
