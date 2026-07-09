---
title: "Bản đề xuất"
date: 2026-05-11
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

# Mimi Jewelry E-commerce Platform

## Giải pháp thương mại điện tử Serverless trên AWS

### 1. Tóm tắt điều hành

AWS Serverless E-commerce Platform là hệ thống website thương mại điện tử được xây dựng và triển khai trên nền tảng AWS theo mô hình serverless. Dự án cho phép người dùng truy cập website, xem danh sách sản phẩm, xem chi tiết sản phẩm, đặt hàng, thanh toán trực tuyến và theo dõi trạng thái đơn hàng.

Hệ thống có trang quản trị dành cho admin để quản lý sản phẩm, hình ảnh sản phẩm, đơn hàng, trạng thái thanh toán và hoàn tiền. Dự án sử dụng các dịch vụ AWS như Amazon Route 53, AWS WAF, Amazon CloudFront, Amazon S3, Amazon Cognito, Amazon API Gateway, AWS Lambda, Amazon DynamoDB, Amazon EventBridge, Amazon CloudWatch, Amazon SNS, AWS IAM và AWS CloudFormation.

Ngoài ra, hệ thống tích hợp ZaloPay làm dịch vụ thanh toán bên thứ ba và sử dụng GitHub Actions để tự động hóa quá trình triển khai. Mục tiêu của dự án là xây dựng một hệ thống ecommerce có thể hoạt động thực tế, dễ mở rộng, giảm việc quản lý server thủ công và phù hợp với kiến trúc cloud hiện đại.

### 2. Tuyên bố vấn đề

_Vấn đề hiện tại_  
Các website thương mại điện tử truyền thống thường cần server backend, database server, hệ thống lưu trữ hình ảnh, hệ thống xác thực người dùng, thanh toán, monitoring và CI/CD. Nếu triển khai theo mô hình server truyền thống, người phát triển phải tự quản lý máy chủ, cấu hình bảo mật, scaling, backup, logging và xử lý lỗi vận hành.

Điều này gây khó khăn cho các dự án cá nhân hoặc nhóm nhỏ vì cần nhiều thời gian cấu hình hạ tầng, chi phí có thể tăng nếu server chạy liên tục, đồng thời việc mở rộng khi lượng truy cập tăng cũng phức tạp hơn.

_Giải pháp_  
Dự án sử dụng kiến trúc AWS Serverless để giảm việc quản lý máy chủ. Người dùng truy cập website thông qua domain được quản lý bởi Amazon Route 53. Request đi qua Amazon CloudFront để phân phối nội dung nhanh hơn. AWS WAF được bổ sung trước CloudFront để kiểm tra request và tăng cường bảo vệ ứng dụng khỏi các request không hợp lệ hoặc độc hại.

Frontend được lưu trong Amazon S3 Frontend Bucket và phân phối qua CloudFront. Người dùng và admin đăng nhập thông qua Amazon Cognito. API request từ frontend đi qua Amazon API Gateway và được xử lý bằng AWS Lambda. Dữ liệu sản phẩm và đơn hàng được lưu trong Amazon DynamoDB.

Hình ảnh sản phẩm được lưu riêng trong Amazon S3 Product Image Bucket. Khi admin upload hình ảnh, backend tạo upload URL để ảnh được lưu vào S3, sau đó CloudFront phân phối ảnh sản phẩm đến người dùng.

Hệ thống tích hợp ZaloPay làm cổng thanh toán bên thứ ba. Khi người dùng thanh toán, Lambda tạo yêu cầu thanh toán và gửi đến ZaloPay. Sau khi thanh toán, ZaloPay callback về hệ thống để cập nhật trạng thái đơn hàng.

Amazon EventBridge được dùng để kích hoạt các tác vụ nền theo lịch như kiểm tra đơn hàng quá hạn thanh toán và đối soát hoàn tiền. Amazon CloudWatch ghi logs và metrics, Amazon SNS gửi cảnh báo đến email khi có lỗi hệ thống.

_Lợi ích và hoàn vốn đầu tư (ROI)_  
Giải pháp giúp giảm nhu cầu vận hành server, dễ mở rộng theo số lượng request và phù hợp với hệ thống ecommerce quy mô nhỏ đến trung bình. Việc sử dụng các dịch vụ serverless như S3, CloudFront, API Gateway, Lambda và DynamoDB giúp tối ưu chi phí vì hệ thống chủ yếu tính phí theo mức sử dụng thực tế.

Dự án cũng giúp người học hiểu cách triển khai một ứng dụng web thực tế trên AWS, bao gồm frontend hosting, backend serverless, database NoSQL, authentication, file upload, payment integration, monitoring, alerting và CI/CD.

### 3. Kiến trúc giải pháp

Hệ thống được thiết kế theo kiến trúc AWS Serverless. Người dùng truy cập website thông qua Amazon Route 53. Route 53 điều hướng request đến Amazon CloudFront. Trước CloudFront, hệ thống có AWS WAF để kiểm tra request và hỗ trợ bảo vệ ứng dụng khỏi các truy cập bất thường.

CloudFront phân phối frontend từ Amazon S3 Frontend Bucket. Frontend là static website được build từ source code và lưu trong S3. Khi người dùng truy cập website, CloudFront phục vụ các file static như HTML, CSS và JavaScript.

Hệ thống sử dụng Amazon Cognito để xác thực người dùng. Cognito quản lý quá trình đăng nhập và trả về token xác thực. Token này được frontend gửi kèm trong các request đến Amazon API Gateway. API Gateway đóng vai trò là API Layer, tiếp nhận request và invoke AWS Lambda để xử lý nghiệp vụ.

Compute Layer của hệ thống sử dụng AWS Lambda. Các Lambda chính gồm EcommerceBackendFunction, RefundReconciliationFunction và PaymentExpirySchedulerFunction. EcommerceBackendFunction xử lý các nghiệp vụ chính như quản lý sản phẩm, đơn hàng, checkout, upload hình ảnh, thanh toán và admin operations. RefundReconciliationFunction dùng để đối soát hoàn tiền. PaymentExpirySchedulerFunction dùng để kiểm tra các đơn hàng chờ thanh toán nhưng đã quá hạn.

Data Layer sử dụng Amazon DynamoDB để lưu dữ liệu. Các bảng chính gồm Products và Orders. Products lưu thông tin sản phẩm, giá, mô tả, hình ảnh, tồn kho và trạng thái sản phẩm. Orders lưu thông tin đơn hàng, khách hàng, trạng thái thanh toán và trạng thái xử lý đơn hàng.

S3 Product Image Bucket được dùng để lưu hình ảnh sản phẩm. Khi admin upload ảnh, backend xử lý upload image và lưu ảnh vào bucket này. Sau đó ảnh được dùng để hiển thị trên website.

Integration Layer gồm Amazon EventBridge và ZaloPay. EventBridge kích hoạt các Lambda chạy nền theo lịch. ZaloPay là Third Party Service dùng để xử lý thanh toán trực tuyến. Lambda gửi payment request đến ZaloPay, sau đó ZaloPay trả kết quả thanh toán về hệ thống.

Monitoring Layer gồm Amazon CloudWatch, Amazon SNS, Amazon Cognito AdminPool và Alert Email. CloudWatch ghi logs và metrics từ API Gateway, Lambda và các service liên quan. Khi phát sinh lỗi hoặc vượt ngưỡng cảnh báo, CloudWatch gửi alarm đến SNS. SNS tiếp tục gửi thông báo đến email admin. AdminPool Cognito được dùng để xác thực admin trong hệ thống quản trị và hỗ trợ kiểm soát quyền truy cập của admin.

CI/CD Layer sử dụng GitHub, GitHub Actions, IAM OIDC Role và CloudFormation. Developer push code lên GitHub. GitHub Actions build và deploy hệ thống lên AWS thông qua IAM OIDC Role. CloudFormation triển khai các tài nguyên như Lambda Function, API Gateway, S3 Frontend, CloudFront Invalidation và các tài nguyên liên quan.

<img src="/workshop-/images/2-Proposal/aws-ecommerce-architecture.png" alt="AWS Serverless E-commerce Architecture" style="max-width: 100%; height: auto;">

_Dịch vụ AWS sử dụng_

- _Amazon Route 53_: Quản lý domain và DNS cho website.
- _AWS WAF_: Kiểm tra request và tăng cường bảo vệ ứng dụng trước CloudFront.
- _Amazon CloudFront_: Phân phối frontend và nội dung tĩnh thông qua CDN.
- _Amazon S3 Frontend Bucket_: Lưu trữ static files của frontend.
- _Amazon S3 Product Image Bucket_: Lưu trữ hình ảnh sản phẩm.
- _Amazon Cognito_: Quản lý đăng nhập và xác thực người dùng/admin.
- _Amazon API Gateway_: Tiếp nhận request từ frontend và chuyển đến Lambda.
- _AWS Lambda_: Xử lý backend logic, đơn hàng, sản phẩm, thanh toán, upload ảnh và tác vụ nền.
- _Amazon DynamoDB_: Lưu dữ liệu sản phẩm và đơn hàng.
- _Amazon EventBridge_: Kích hoạt Lambda chạy nền theo lịch.
- _Amazon CloudWatch_: Ghi logs, metrics và hỗ trợ tạo alarm.
- _Amazon SNS_: Gửi cảnh báo vận hành qua email.
- _AWS IAM_: Quản lý quyền truy cập giữa các dịch vụ.
- _AWS CloudFormation_: Triển khai và quản lý hạ tầng bằng template.

_Dịch vụ bên thứ ba_

- _ZaloPay_: Cổng thanh toán bên thứ ba để xử lý giao dịch thanh toán.
- _GitHub Actions_: Tự động hóa quy trình build và deploy.

_Thiết kế thành phần_

- _User Layer_: Người dùng truy cập website thông qua domain.
- _DNS Layer_: Route 53 điều hướng request đến CloudFront.
- _Security Layer_: AWS WAF kiểm tra request trước khi vào CloudFront.
- _Frontend Layer_: CloudFront phân phối frontend từ S3 Frontend Bucket.
- _Authentication Layer_: Cognito quản lý đăng nhập và token xác thực.
- _API Layer_: API Gateway tiếp nhận request và gọi Lambda.
- _Compute Layer_: AWS Lambda xử lý toàn bộ nghiệp vụ backend.
- _Data Layer_: DynamoDB lưu Products và Orders.
- _Storage Layer_: S3 Product Image Bucket lưu hình ảnh sản phẩm.
- _Integration Layer_: EventBridge xử lý tác vụ nền, ZaloPay xử lý thanh toán.
- _Monitoring Layer_: CloudWatch, SNS và Alert Email theo dõi lỗi hệ thống.
- _CI/CD Layer_: GitHub Actions, IAM OIDC Role và CloudFormation triển khai hệ thống.

### 4. Triển khai kỹ thuật

_Các giai đoạn triển khai_

1. _Nghiên cứu dịch vụ AWS_: Tìm hiểu S3, CloudFront, Route 53, WAF, Cognito, API Gateway, Lambda, DynamoDB, EventBridge, CloudWatch, SNS, IAM và CloudFormation.
2. _Thiết kế kiến trúc_: Xây dựng sơ đồ kiến trúc serverless cho hệ thống ecommerce.
3. _Phát triển frontend_: Xây dựng giao diện website bán hàng, trang sản phẩm, checkout và trang admin.
4. _Phát triển backend_: Xây dựng backend bằng Node.js/TypeScript chạy trên AWS Lambda.
5. _Cấu hình API Layer_: Tạo API Gateway để tiếp nhận request từ frontend.
6. _Tích hợp database_: Sử dụng DynamoDB để lưu Products và Orders.
7. _Tích hợp authentication_: Sử dụng Cognito cho đăng nhập user/admin.
8. _Triển khai frontend_: Upload static frontend lên S3 và phân phối qua CloudFront.
9. _Bổ sung bảo mật_: Cấu hình AWS WAF để kiểm tra request vào CloudFront.
10. _Upload hình ảnh_: Sử dụng S3 Product Image Bucket để lưu ảnh sản phẩm.
11. _Tích hợp thanh toán_: Tích hợp ZaloPay để xử lý payment request và callback.
12. _Tác vụ nền_: Dùng EventBridge để trigger Lambda theo lịch.
13. _Monitoring và alert_: Cấu hình CloudWatch, SNS và Alert Email.
14. _CI/CD_: Sử dụng GitHub Actions, IAM OIDC Role và CloudFormation để deploy tự động.

_Yêu cầu kỹ thuật_

- _Frontend_: Static website, lưu trữ trên S3 và phân phối qua CloudFront.
- _Backend_: Node.js/TypeScript, AWS Lambda, API Gateway.
- _Database_: DynamoDB với bảng Products và Orders.
- _Authentication_: Amazon Cognito cho user/admin.
- _Security_: AWS WAF, IAM Policy, private S3 bucket và CloudFront.
- _Storage_: S3 Frontend Bucket và S3 Product Image Bucket.
- _Payment_: ZaloPay third-party payment service.
- _Monitoring_: CloudWatch Logs, Metrics, Alarm và SNS.
- _Deployment_: GitHub Actions, IAM OIDC Role và CloudFormation.

### 5. Lộ trình & Mốc triển khai

- _Tuần 1–3_: Học các dịch vụ AWS nền tảng và serverless.
  - Tìm hiểu AWS Console, IAM, S3, CloudFront, Route 53, WAF, DynamoDB, Cognito, Lambda, API Gateway, EventBridge, CloudWatch và SNS.

- _Tuần 4_: Phân tích yêu cầu và thiết kế kiến trúc.
  - Xác định chức năng hệ thống.
  - Vẽ sơ đồ kiến trúc serverless.
  - Xác định các dịch vụ AWS sử dụng.

- _Tuần 5_: Xây dựng frontend.
  - Trang chủ, danh sách sản phẩm, chi tiết sản phẩm.
  - Giỏ hàng, checkout và trang admin.

- _Tuần 6_: Xây dựng backend.
  - Tạo Lambda backend.
  - Cấu hình API Gateway.
  - Xây dựng API sản phẩm, đơn hàng và admin.

- _Tuần 7_: Tích hợp DynamoDB.
  - Thiết kế Products và Orders tables.
  - Kết nối Lambda với DynamoDB.

- _Tuần 8_: Tích hợp Cognito.
  - Cấu hình đăng nhập user/admin.
  - Xử lý JWT token và phân quyền API.

- _Tuần 9_: Deploy frontend.
  - Build frontend.
  - Upload lên S3.
  - Cấu hình CloudFront.

- _Tuần 10_: Upload ảnh và thanh toán.
  - S3 Product Image Bucket.
  - Upload image.
  - ZaloPay payment request và callback.

- _Tuần 11_: Scheduled jobs và monitoring.
  - EventBridge.
  - PaymentExpirySchedulerFunction.
  - RefundReconciliationFunction.
  - CloudWatch và SNS.

- _Tuần 12_: Hoàn thiện CI/CD, bảo mật và tài liệu.
  - GitHub Actions.
  - IAM OIDC Role.
  - CloudFormation.
  - Proposal, Workshop, Worklog và Clean-up.

### 6. Ước tính ngân sách

Chi phí dự án phụ thuộc vào lượng request, dung lượng lưu trữ, traffic CloudFront, số lượng log CloudWatch và việc có sử dụng domain riêng hay không.

_Chi phí hạ tầng dự kiến cho giai đoạn học tập/demo_

- Amazon S3: Lưu frontend và hình ảnh sản phẩm.
- Amazon CloudFront: Phân phối nội dung và hình ảnh.
- AWS WAF: Phát sinh chi phí nếu bật Web ACL và rule.
- AWS Lambda: Tính phí theo số lần gọi và thời gian chạy.
- Amazon API Gateway: Tính phí theo request.
- Amazon DynamoDB: Tính phí theo request đọc/ghi hoặc dung lượng lưu trữ.
- Amazon CloudWatch: Phát sinh chi phí từ logs, metrics và alarms.
- Amazon SNS: Chi phí thấp cho email alert.
- Amazon Route 53: Có phí hosted zone và domain nếu dùng domain riêng.
- AWS CloudFormation: Không tính phí trực tiếp cho việc quản lý stack.

_Tổng chi phí dự kiến_

- _Giai đoạn học tập/demo_: khoảng 0–10 USD/tháng nếu lượng truy cập thấp và cleanup tài nguyên đúng cách.
- _Domain riêng_: tính phí riêng theo năm nếu đăng ký qua Route 53.
- _ZaloPay_: dùng môi trường test/sandbox nên không phát sinh thanh toán thật.

### 7. Đánh giá rủi ro

_Ma trận rủi ro_

- Cấu hình IAM sai hoặc cấp quyền quá rộng: Ảnh hưởng cao, xác suất trung bình.
- Cấu hình WAF sai làm chặn nhầm request hợp lệ: Ảnh hưởng trung bình, xác suất thấp.
- S3 bucket policy hoặc CloudFront sai: Ảnh hưởng trung bình, xác suất trung bình.
- Lỗi Cognito/JWT token khi xác thực người dùng: Ảnh hưởng trung bình, xác suất trung bình.
- Lỗi callback thanh toán từ ZaloPay: Ảnh hưởng cao, xác suất trung bình.
- CloudWatch Logs phát sinh nhiều chi phí nếu không kiểm soát: Ảnh hưởng trung bình, xác suất thấp.
- GitHub Actions deploy lỗi do OIDC hoặc IAM role: Ảnh hưởng trung bình, xác suất trung bình.
- Route 53 domain hoặc HTTPS chưa hoàn tất: Ảnh hưởng thấp đến trung bình, xác suất trung bình.

_Chiến lược giảm thiểu_

- IAM: Áp dụng nguyên tắc least privilege cho từng role.
- WAF: Bắt đầu với rule cơ bản, theo dõi log trước khi chặn mạnh.
- S3/CloudFront: Sử dụng private bucket và chỉ phân phối qua CloudFront.
- Authentication: Kiểm tra JWT token và phân biệt rõ user/admin.
- Payment: Kiểm tra callback URL, secret key và trạng thái đơn hàng.
- Cost control: Cấu hình billing alert và cleanup tài nguyên không sử dụng.
- CI/CD: Giới hạn IAM OIDC Role theo đúng GitHub repository và branch.
- Domain: Nếu Route 53 chưa hoàn tất, dùng CloudFront URL để demo.

_Kế hoạch dự phòng_

- Nếu domain chưa sẵn sàng, sử dụng CloudFront URL.
- Nếu WAF gây lỗi request, tạm thời chuyển rule sang chế độ Count hoặc disable rule.
- Nếu GitHub Actions lỗi, deploy thủ công bằng SAM CLI và AWS CLI.
- Nếu ZaloPay callback lỗi, kiểm tra CloudWatch Logs và cập nhật trạng thái đơn hàng thủ công trong DynamoDB khi cần.
- Nếu CloudFront cache chưa cập nhật, thực hiện CloudFront Invalidation.

### 8. Kết quả kỳ vọng

_Cải tiến kỹ thuật_  
Dự án tạo ra một hệ thống ecommerce serverless có đầy đủ các thành phần chính gồm frontend, backend API, authentication, database, image upload, payment integration, scheduled jobs, monitoring, security layer và CI/CD.

_Giá trị học tập_  
Thông qua dự án, người thực hiện hiểu cách kết hợp nhiều dịch vụ AWS vào một hệ thống thực tế, bao gồm Route 53, WAF, CloudFront, S3, Cognito, API Gateway, Lambda, DynamoDB, EventBridge, CloudWatch, SNS, IAM và CloudFormation.

_Giá trị dài hạn_  
Dự án có thể tiếp tục mở rộng thành hệ thống ecommerce thực tế với domain riêng, HTTPS bằng ACM, dashboard doanh thu, tích hợp đơn vị vận chuyển, thêm cổng thanh toán khác, recommendation system và môi trường staging/production riêng biệt.
