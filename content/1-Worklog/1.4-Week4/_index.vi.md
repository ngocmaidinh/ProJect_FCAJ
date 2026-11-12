
---
title: "Worklog Tuần 4"
date: 2026-08-31
weight: 4
chapter: false
pre: "<b>1.4.</b>"
---

### Mục tiêu tuần 4:

- Tìm hiểu Amazon RDS và hệ quản trị cơ sở dữ liệu MySQL.
- Triển khai Amazon RDS for MySQL để lưu trữ dữ liệu cho website Maiora Fashion Store.
- Cấu hình kết nối riêng tư và an toàn giữa máy chủ ứng dụng EC2 và cơ sở dữ liệu RDS.
- Tích hợp website PHP với cơ sở dữ liệu MySQL.
- Tìm hiểu các cơ chế sao lưu và bảo vệ dữ liệu của Amazon RDS.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
|---|---|---|---|---|
| 2 | Tìm hiểu Amazon RDS, MySQL, DB Instance, Database và các cơ chế sao lưu cơ sở dữ liệu. | 31/08/2026 | 31/08/2026 | [Amazon RDS Documentation](https://docs.aws.amazon.com/rds/) |
| 3 | Tạo Amazon RDS for MySQL, lựa chọn cấu hình DB Instance và thiết lập kết nối mạng trong VPC. | 01/09/2026 | 02/09/2026 | [Amazon RDS Documentation](https://docs.aws.amazon.com/rds/) |
| 4 | Cấu hình Security Group cho RDS và khởi tạo cơ sở dữ liệu `shop` cùng các bảng dữ liệu phục vụ website. | 03/09/2026 | 03/09/2026 | [MySQL Documentation](https://dev.mysql.com/doc/) |
| 5 | Cấu hình PHP trên EC2 kết nối đến RDS bằng tệp cấu hình cơ sở dữ liệu riêng. | 04/09/2026 | 04/09/2026 | [PHP Documentation](https://www.php.net/docs.php) |
| 6 | Kiểm tra khả năng kết nối giữa EC2 và RDS, kiểm tra dữ liệu và chức năng hiển thị sản phẩm trên website. | 05/09/2026 | 05/09/2026 | [Amazon RDS Documentation](https://docs.aws.amazon.com/rds/) |

### Kết quả đạt được tuần 4:

- Hiểu được vai trò của Amazon RDS trong việc triển khai và quản lý cơ sở dữ liệu quan hệ trên AWS.

- Nắm được các thành phần và khái niệm cơ bản:
  - Amazon RDS for MySQL.
  - DB Instance.
  - Database.
  - Table.
  - SQL Query.
  - Database Endpoint.

- Triển khai Amazon RDS for MySQL:
  - Tạo DB Instance sử dụng MySQL.
  - Cấu hình DB Instance trong VPC `backup-dr-vpc`.
  - Thiết lập RDS không cho phép truy cập công khai (Public Access: No).
  - Cấu hình Security Group `rds-sg` để kiểm soát kết nối đến cơ sở dữ liệu.

- Khởi tạo và quản lý cơ sở dữ liệu `shop`:
  - Tạo cơ sở dữ liệu `shop`.
  - Tạo các bảng `users`, `products`, `cart_items`, `orders` và `order_items`.
  - Thêm và truy vấn dữ liệu sản phẩm.
  - Kiểm tra dữ liệu bằng các câu lệnh SQL.
  - Tìm hiểu mối quan hệ giữa các bảng trong cơ sở dữ liệu.

- Thiết lập kết nối giữa website PHP trên EC2 và Amazon RDS:
  - Xác định Database Endpoint.
  - Cấu hình thông tin kết nối trong tệp `/etc/shop/db-config.php`.
  - Sử dụng tài khoản cơ sở dữ liệu riêng cho ứng dụng.
  - Cấu hình Security Group cho phép kết nối MySQL qua TCP port 3306 từ Security Group của máy chủ EC2.
  - Kiểm tra khả năng truy xuất dữ liệu từ website.

- Tìm hiểu các cơ chế sao lưu và bảo vệ dữ liệu của Amazon RDS:
  - Automated Backups.
  - DB Snapshots.
  - Backup Retention Period.
  - Point-in-Time Recovery (PITR).

- Hiểu cách kết hợp Amazon EC2 và Amazon RDS để xây dựng kiến trúc ứng dụng web có cơ sở dữ liệu tập trung, trong đó máy chủ ứng dụng và cơ sở dữ liệu được triển khai tách biệt.

- Hoàn thành việc tích hợp cơ sở dữ liệu với website Maiora Fashion Store, tạo nền tảng cho việc triển khai các cơ chế Backup và Disaster Recovery trong những tuần tiếp theo.
