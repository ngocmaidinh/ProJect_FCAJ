
---
title: "Worklog Tuần 5"
date: 2026-09-07
weight: 5
chapter: false
pre: "<b>1.5.</b>"
---

### Mục tiêu tuần 5:

- Tìm hiểu Amazon S3 và cơ chế lưu trữ đối tượng trên AWS.
- Triển khai S3 Bucket để lưu trữ hình ảnh sản phẩm của website Maiora Fashion Store.
- Tích hợp Amazon S3 với website PHP nhằm tách biệt dữ liệu hình ảnh khỏi máy chủ ứng dụng.
- Cấu hình S3 Versioning để bảo vệ và quản lý các phiên bản đối tượng.
- Tìm hiểu và triển khai Cross-Region Replication để sao chép dữ liệu từ Region Singapore sang Region Sydney.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
|---|---|---|---|---|
| 2 | Tìm hiểu Amazon S3, Bucket, Object, Object Key và các lớp lưu trữ. | 07/09/2026 | 07/09/2026 | [Amazon S3 Documentation](https://docs.aws.amazon.com/s3/) |
| 3 | Tạo S3 Bucket tại Region Singapore và tải hình ảnh sản phẩm lên thư mục `products/`. | 08/09/2026 | 08/09/2026 | [Amazon S3 Documentation](https://docs.aws.amazon.com/s3/) |
| 4 | Cấu hình quyền truy cập và tích hợp đường dẫn hình ảnh S3 vào website Maiora Fashion Store. | 09/09/2026 | 10/09/2026 | [Amazon S3 Documentation](https://docs.aws.amazon.com/s3/) |
| 5 | Bật S3 Versioning, tìm hiểu cách quản lý phiên bản đối tượng và các chính sách bảo vệ dữ liệu. | 11/09/2026 | 11/09/2026 | [Managing S3 Versioning](https://docs.aws.amazon.com/AmazonS3/latest/userguide/Versioning.html) |
| 6 | Tạo bucket tại Region Sydney và cấu hình Cross-Region Replication từ Singapore sang Sydney. | 12/09/2026 | 12/09/2026 | [S3 Replication Documentation](https://docs.aws.amazon.com/AmazonS3/latest/userguide/replication.html) |

### Kết quả đạt được tuần 5:

- Hiểu được Amazon S3 và vai trò của dịch vụ trong việc lưu trữ, quản lý và bảo vệ dữ liệu đối tượng trên AWS.

- Nắm được các thành phần cơ bản của Amazon S3:
  - Bucket.
  - Object.
  - Object Key.
  - Bucket Policy.
  - Storage Class.

- Triển khai lưu trữ hình ảnh sản phẩm trên Amazon S3:
  - Tạo S3 Bucket tại Region Singapore.
  - Tải hình ảnh sản phẩm lên bucket.
  - Sắp xếp hình ảnh trong thư mục `products/`.
  - Kiểm tra và quản lý các đối tượng được lưu trữ.

- Tích hợp Amazon S3 với website Maiora Fashion Store:
  - Cấu hình đường dẫn lưu trữ hình ảnh.
  - Điều chỉnh ứng dụng PHP để lấy hình ảnh từ S3 thay vì lưu trữ trực tiếp trên máy chủ EC2.
  - Kiểm tra khả năng hiển thị hình ảnh sản phẩm trên website.

- Tìm hiểu và cấu hình các cơ chế bảo vệ dữ liệu S3:
  - S3 Versioning.
  - S3 Cross-Region Replication.
  - IAM Policy.
  - S3 Bucket Policy.
  - Block Public Access và các tùy chọn kiểm soát quyền truy cập.

- Hiểu cách S3 Versioning lưu giữ nhiều phiên bản của một đối tượng, hỗ trợ truy xuất phiên bản trước đó khi dữ liệu bị ghi đè hoặc xóa nhầm.

- Tìm hiểu và triển khai S3 Cross-Region Replication:
  - Sử dụng Region Singapore (`ap-southeast-1`) làm Region nguồn.
  - Sử dụng Region Sydney (`ap-southeast-2`) làm Region đích.
  - Cấu hình bucket đích và quyền IAM phục vụ quá trình replication.
  - Thiết lập quy tắc sao chép các đối tượng đáp ứng điều kiện cấu hình.
  - Kiểm tra sự xuất hiện của dữ liệu được sao chép tại bucket đích.

- Hiểu sự khác biệt giữa S3 Versioning và Cross-Region Replication, cũng như vai trò của từng cơ chế trong chiến lược bảo vệ dữ liệu.

- Hoàn thành việc đưa dữ liệu hình ảnh sản phẩm lên S3 và xây dựng cơ chế bảo vệ dữ liệu hình ảnh giữa hai AWS Region, tạo nền tảng cho các thử nghiệm khôi phục trong những tuần tiếp theo.
