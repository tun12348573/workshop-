---
title: "Worklog Tuần 12"
date: 2026-07-06
weight: 12
chapter: false
pre: " <b> 1.12 </b> "
---

### Mục tiêu tuần 12:

- Hoàn thiện CI/CD, bảo mật, tài liệu và chuẩn bị báo cáo dự án.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc                                                                                                                                                                                         | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | -------------- |
| 2   | - Thiết lập GitHub repository và GitHub Actions workflow để build, test và chuẩn bị deploy dự án.                                                                                                 | 06/07/2026   | 06/07/2026      |
| 3   | - Cấu hình AWS IAM OIDC Role cho GitHub Actions, giúp GitHub có thể deploy lên AWS mà không cần hard-code Access Key.                                                                             | 07/07/2026   | 07/07/2026      |                |
| 4   | - Hoàn thiện deploy bằng AWS SAM và CloudFormation. Quản lý các tài nguyên như Lambda, API Gateway, DynamoDB, S3, CloudFront, IAM, EventBridge, CloudWatch và SNS bằng template.                  | 08/07/2026   | 08/07/2026      |                |
| 5   | - Rà soát bảo mật của hệ thống: IAM policies, Cognito authentication, S3 bucket policy, CloudFront OAC, quyền Lambda với DynamoDB/S3 và quyền GitHub Actions deploy. - Hoàn thiện tài liệu dự án. | 09/07/2026   | 09/07/2026      |                |

### Kết quả đạt được tuần 12:

- Dự án hoàn thiện đầy đủ các chức năng chính, có CI/CD, monitoring, bảo mật cơ bản và tài liệu mô tả hệ thống.
