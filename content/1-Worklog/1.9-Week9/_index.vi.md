---
title: "Worklog Tuần 9"
date: 2026-06-15
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

### Mục tiêu tuần 9:

- Deploy frontend lên Amazon S3 và CloudFront.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc                                                                                                          | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | ------------------------------------------------------------------------------------------------------------------ | ------------ | --------------- | -------------- |
| 2   | - Cấu hình frontend để build static site. Kiểm tra quá trình build và xử lý các lỗi phát sinh khi export frontend. | 15/06/2026   | 15/06/2026      |
| 3   | - Tạo S3 Frontend Bucket và upload các file build của frontend lên bucket.                                         | 16/06/2026   | 16/06/2026      |                |
| 4   | - Cấu hình CloudFront Distribution để phân phối frontend từ S3 và kiểm tra website qua CloudFront URL.             | 17/06/2026   | 17/06/2026      |                |
| 5   | - Kiểm tra lỗi route frontend, asset path, cache và các trang khi refresh trực tiếp trên CloudFront.               | 18/06/2026   | 18/06/2026      |                |
| 6   | - Cấu hình CloudFront invalidation để cập nhật nội dung mới sau mỗi lần deploy frontend.                           | 19/06/2026   | 19/06/2026      |                |

### Kết quả đạt được tuần 9:

- Website đã được deploy online thông qua S3 và CloudFront, có thể truy cập bằng CloudFront URL.
