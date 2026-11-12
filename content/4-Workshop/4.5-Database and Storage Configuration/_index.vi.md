
---
title: "Cấu hình cơ sở dữ liệu và lưu trữ"
date: 2026-10-31
weight: 5
chapter: false
pre: "<b>4.5.</b>"
---

## 4.5. Cấu hình cơ sở dữ liệu và lưu trữ

Trong phần này, Amazon RDS và Amazon S3 được cấu hình để cung cấp dịch vụ cơ sở dữ liệu và lưu trữ đối tượng cho ứng dụng Maiora Fashion Store.

Cơ sở dữ liệu lưu trữ các thông tin của ứng dụng như tài khoản người dùng, thông tin sản phẩm, giỏ hàng và đơn hàng. Amazon S3 được sử dụng để lưu trữ hình ảnh sản phẩm độc lập với máy chủ ứng dụng EC2.

### 4.5.1. Khởi tạo Amazon RDS MySQL

Amazon RDS for MySQL được sử dụng làm dịch vụ cơ sở dữ liệu quan hệ cho ứng dụng.

Thông tin cấu hình cơ sở dữ liệu:

- Hệ quản trị cơ sở dữ liệu: MySQL.
- DB instance identifier: `backup-dr-db`.
- Loại phiên bản: `db.t3.micro`.
- Dung lượng lưu trữ: 20 GB.
- Tên cơ sở dữ liệu: `shop`.
- Public access: No.
- VPC: `backup-dr-vpc`.
- Security Group: `rds-sg`.

RDS được triển khai trong mạng riêng nhằm hạn chế khả năng truy cập trực tiếp từ Internet.

![Cấu hình RDS Instance](/ProJect_FCAJ/images/4-Workshop/4.5-Database-and-Storage-Configuration/rds-instance.png)

### 4.5.2. Cấu hình kết nối cơ sở dữ liệu

Security Group của RDS được cấu hình cho phép kết nối MySQL thông qua TCP port 3306 chỉ từ Security Group của máy chủ ứng dụng EC2.

Cấu hình này đảm bảo máy chủ ứng dụng có thể truy cập cơ sở dữ liệu mà không cần công khai RDS ra Internet.

Ứng dụng sử dụng một tệp cấu hình riêng để lưu trữ thông tin kết nối cơ sở dữ liệu. Các thông tin nhạy cảm như mật khẩu không được lưu trong mã nguồn công khai trên GitHub.

![Cấu hình kết nối RDS](/ProJect_FCAJ/images/4-Workshop/4.5-Database-and-Storage-Configuration/rds-connectivity.png)

### 4.5.3. Khởi tạo cơ sở dữ liệu ứng dụng

Sau khi RDS được khởi tạo thành công, cơ sở dữ liệu `shop` được chuẩn bị để phục vụ ứng dụng Maiora Fashion Store.

Cơ sở dữ liệu bao gồm các bảng phục vụ những chức năng chính của website:

- `users`: lưu trữ thông tin tài khoản khách hàng.
- `products`: lưu trữ thông tin sản phẩm.
- `cart_items`: lưu trữ các sản phẩm trong giỏ hàng.
- `orders`: lưu trữ thông tin đơn hàng.
- `order_items`: lưu trữ chi tiết sản phẩm thuộc từng đơn hàng.

Các bảng dữ liệu hỗ trợ những chức năng chính như đăng ký tài khoản, đăng nhập, hiển thị sản phẩm, quản lý giỏ hàng và xử lý đơn hàng.

![Các bảng trong cơ sở dữ liệu](/ProJect_FCAJ/images/4-Workshop/4.5-Database-and-Storage-Configuration/database-tables.png)

### 4.5.4. Tạo Amazon S3 Bucket

Amazon S3 được sử dụng để lưu trữ hình ảnh sản phẩm độc lập với máy chủ ứng dụng EC2.

Một S3 Bucket riêng được tạo để lưu trữ các hình ảnh của website.

Thông tin cấu hình:

- Tên Bucket: `myproject-backup-primary-671657`.
- AWS Region: Asia Pacific (Singapore).
- Object ownership: Bucket owner enforced.
- Block Public Access: cấu hình phù hợp với phương thức truy cập hình ảnh của ứng dụng.
- Mã hóa phía máy chủ: SSE-S3.

Ứng dụng sử dụng vị trí lưu trữ của các đối tượng trên S3 để truy xuất và hiển thị hình ảnh sản phẩm.

![Cấu hình S3 Bucket](/ProJect_FCAJ/images/4-Workshop/4.5-Database-and-Storage-Configuration/s3-bucket.png)

### 4.5.5. Tải hình ảnh sản phẩm lên Amazon S3

Các hình ảnh sản phẩm được tải lên thư mục tiền tố `products/` trong S3 Bucket.

Ứng dụng truy xuất đường dẫn hình ảnh từ cơ sở dữ liệu và sử dụng đường dẫn tương ứng để hiển thị hình ảnh trên website.

Việc tách riêng hình ảnh sản phẩm khỏi máy chủ ứng dụng giúp quản lý dữ liệu lưu trữ linh hoạt hơn và tạo cơ sở cho việc triển khai đồng bộ dữ liệu liên vùng ở phần tiếp theo.

![Hình ảnh sản phẩm trên S3](/ProJect_FCAJ/images/4-Workshop/4.5-Database-and-Storage-Configuration/s3-product-images.png)

### 4.5.6. Tổng kết

Trong phần này, Amazon RDS for MySQL và Amazon S3 được cấu hình để phục vụ ứng dụng Maiora Fashion Store.

Amazon RDS cung cấp dịch vụ lưu trữ cơ sở dữ liệu quan hệ tập trung, trong khi Amazon S3 lưu trữ hình ảnh sản phẩm độc lập với máy chủ ứng dụng EC2.

Hai dịch vụ này tạo nền tảng dữ liệu và lưu trữ cho việc triển khai giải pháp Backup và Disaster Recovery trong các phần tiếp theo.
