---
title: "Blog 2"
date: 2026-07-06
weight: 2
chapter: false
pre: " <b> 3.2. </b> "
---

# TỰ ĐỘNG GIẢI NÉN FILE TRÊN AMAZON S3 BẰNG AWS BATCH VÀ AMAZON ECS

Trong quá trình tìm hiểu về AWS Batch, em đã đọc bài viết **"Automated extraction of compressed files on Amazon S3 using AWS Batch and Amazon ECS"** trên AWS Storage Blog.

Điều em ấn tượng nhất ở giải pháp này là khả năng xây dựng một quy trình xử lý dữ liệu hoàn toàn tự động theo mô hình **event-driven architecture**. Khi có file nén được upload lên Amazon S3, hệ thống sẽ tự động kích hoạt AWS Batch để chạy container xử lý file, giải nén dữ liệu và lưu kết quả trở lại S3.

Thay vì duy trì một máy chủ EC2 chạy liên tục để theo dõi và giải nén file, kiến trúc này chỉ tạo tài nguyên tính toán khi có công việc cần xử lý. Đây là cách tiếp cận giúp tối ưu chi phí và giảm công sức quản lý hạ tầng.

## 1. Bài toán đặt ra

Giả sử một doanh nghiệp thường xuyên nhận dữ liệu từ nhiều đối tác. Các đối tác tải lên các file nén có dung lượng lớn như `.tar` lên Amazon S3.

Bên trong mỗi file có thể chứa hàng nghìn hình ảnh, tài liệu hoặc dữ liệu cần xử lý.

Ví dụ:

```text
backup.tar
├── image01.jpg
├── image02.jpg
├── image03.jpg
├── report.csv
└── ...
```

Tuy nhiên, các hệ thống phía sau thường chỉ xử lý được từng file riêng lẻ thay vì xử lý trực tiếp toàn bộ file TAR. Vì vậy cần có một bước trung gian để:

- Phát hiện khi có file mới được upload.
- Giải nén file.
- Đưa các file đã giải nén trở lại Amazon S3.
- Cho phép các hệ thống khác tiếp tục xử lý dữ liệu.

Nếu triển khai theo cách truyền thống, có thể cần duy trì một EC2 chạy liên tục để theo dõi bucket và giải nén file. Cách này gây tốn chi phí và cần quản lý server thủ công.

## 2. Kiến trúc tổng thể

Theo cách em hiểu, kiến trúc hoạt động như sau:

```text
Upload TAR File
   ↓
Amazon S3
   ↓
Amazon EventBridge
   ↓
AWS Batch
   ↓
Amazon ECS Container
   ↓
Download → Extract → Upload
   ↓
Amazon S3 Output
```

Điểm nổi bật là không có server nào chạy thường trực. Khi không có file mới, hệ thống gần như không tiêu tốn tài nguyên tính toán.

<img src="/workshop-/images/3-BlogsPosted/blog2-s3-batch-ecs.png" alt="Automated File Extraction Architecture" style="max-width: 100%; height: auto;">

## 3. Vai trò của từng dịch vụ

### Amazon S3

Amazon S3 là nơi lưu trữ dữ liệu đầu vào và đầu ra. Khi người dùng upload file TAR lên bucket, S3 phát sinh sự kiện Object Created. Sau khi quá trình giải nén hoàn tất, các file kết quả được upload trở lại S3.

### Amazon EventBridge

Amazon EventBridge đóng vai trò điều phối sự kiện. EventBridge lắng nghe sự kiện từ Amazon S3 và khi phát hiện có file mới được upload, nó sẽ gửi yêu cầu tạo AWS Batch Job.

### AWS Batch

AWS Batch là dịch vụ chịu trách nhiệm quản lý quá trình xử lý batch job. AWS Batch nhận yêu cầu xử lý, chọn tài nguyên tính toán phù hợp, khởi tạo môi trường chạy container và giải phóng tài nguyên sau khi job hoàn tất.

Điều em học được là AWS Batch không chỉ phù hợp với Machine Learning hoặc High Performance Computing, mà còn rất hữu ích cho các tác vụ xử lý dữ liệu theo lô.

### Amazon ECS

AWS Batch chạy logic xử lý thông qua container trên Amazon ECS. Container sẽ thực hiện các bước:

- Download file từ S3.
- Giải nén file.
- Upload kết quả trở lại S3.

Việc đóng gói logic trong Docker container giúp quy trình dễ bảo trì, dễ cập nhật và dễ mở rộng.

### Amazon EBS

Container không giải nén trực tiếp trên S3. Thay vào đó, file TAR được download về vùng lưu trữ tạm thời như Amazon EBS. Quy trình xử lý diễn ra như sau:

1. Download file TAR từ S3 về EBS.
2. Giải nén file trên EBS.
3. Upload file kết quả trở lại S3.
4. Giải phóng tài nguyên sau khi Batch Job hoàn tất.

## 4. Luồng hoạt động

Hệ thống hoạt động theo các bước sau:

1. Người dùng upload file TAR lên Amazon S3.
2. Amazon S3 phát sinh sự kiện Object Created.
3. Amazon EventBridge nhận sự kiện.
4. EventBridge gửi yêu cầu tạo AWS Batch Job.
5. AWS Batch khởi tạo môi trường tính toán.
6. AWS Batch chạy container thông qua Amazon ECS.
7. Container download file TAR từ S3.
8. File được giải nén trên vùng lưu trữ tạm thời.
9. Các file sau khi giải nén được upload trở lại Amazon S3.
10. Batch Job kết thúc và tài nguyên được giải phóng.

## 5. Tại sao dùng AWS Batch thay vì AWS Lambda?

Ban đầu em cũng đặt câu hỏi vì sao không dùng AWS Lambda cho bài toán này.

Sau khi tìm hiểu, em nhận ra nguyên nhân chính là kích thước dữ liệu và thời gian xử lý. Các file TAR trong thực tế có thể có dung lượng rất lớn, thậm chí hàng chục hoặc hàng trăm GB. Với khối lượng dữ liệu như vậy, Lambda có thể gặp giới hạn về:

- Thời gian thực thi.
- Dung lượng lưu trữ tạm thời.
- Tài nguyên CPU/RAM.
- Khả năng xử lý workload dài.

Trong khi đó, AWS Batch có thể lựa chọn tài nguyên tính toán phù hợp, chạy container và xử lý workload lớn linh hoạt hơn.

Vì vậy, AWS Batch là lựa chọn phù hợp hơn cho các tác vụ xử lý dữ liệu theo lô có dung lượng lớn hoặc thời gian xử lý dài.

## 6. Điều em học được

Sau khi đọc bài blog, em rút ra một số điểm đáng chú ý.

Thứ nhất, không phải mọi bài toán xử lý file đều nên dùng Lambda. Với workload lớn hoặc thời gian xử lý dài, AWS Batch là lựa chọn phù hợp hơn.

Thứ hai, kiến trúc event-driven giúp hệ thống chỉ tiêu tốn tài nguyên khi có dữ liệu mới cần xử lý. Điều này giúp tối ưu chi phí vận hành.

Thứ ba, việc đóng gói logic xử lý trong Docker container giúp hệ thống dễ bảo trì và mở rộng.

Theo em, kiến trúc này không chỉ phù hợp với bài toán giải nén file mà còn có thể áp dụng cho nhiều bài toán khác như:

- Resize hình ảnh hàng loạt.
- Chuyển đổi định dạng video.
- Chuyển đổi CSV sang Parquet.
- Phân tích log.
- OCR tài liệu.
- AI Batch Inference.
- ETL Pipeline.

## 7. Kết luận

Thông qua việc tìm hiểu bài blog này, em hiểu rõ hơn cách kết hợp Amazon S3, Amazon EventBridge, AWS Batch và Amazon ECS để xây dựng một pipeline xử lý dữ liệu tự động.

Điều em đánh giá cao nhất ở kiến trúc này là khả năng tối ưu chi phí nhờ mô hình pay-as-you-go, khả năng mở rộng linh hoạt và giảm đáng kể công sức quản trị hạ tầng.

Trong thời gian tới, em muốn thử triển khai lại kiến trúc này theo từng bước để hiểu sâu hơn cách các dịch vụ AWS phối hợp trong một hệ thống xử lý dữ liệu thực tế.

## 8. Tài liệu tham khảo

- AWS Storage Blog: Automated extraction of compressed files on Amazon S3 using AWS Batch and Amazon ECS
- Amazon S3 Documentation
- Amazon EventBridge Documentation
- AWS Batch Documentation
- Amazon ECS Documentation
- Amazon EBS Documentation
