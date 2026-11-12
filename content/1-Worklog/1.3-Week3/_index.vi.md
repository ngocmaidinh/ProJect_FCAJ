
---
title: "Worklog Tuần 3"
date: 2026-08-24
weight: 3
chapter: false
pre: "<b>1.3.</b>"
---

### Mục tiêu tuần 3:

- Tìm hiểu môi trường Linux và các thao tác quản trị máy chủ EC2.
- Cài đặt và cấu hình môi trường máy chủ web trên Amazon Linux.
- Tìm hiểu Apache HTTP Server, PHP và PHP-FPM.
- Xây dựng và triển khai website thương mại điện tử Maiora Fashion Store.
- Kiểm tra khả năng truy cập website và xử lý các lỗi cơ bản.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
|---|---|---|---|---|
| 2 | Tìm hiểu Amazon Linux, hệ thống tệp, quyền truy cập và các lệnh quản trị Linux cơ bản. | 24/08/2026 | 24/08/2026 | [AWS Cloud Journey](https://cloudjourney.awsstudygroup.com/) |
| 3 | Cài đặt và cấu hình Apache HTTP Server trên EC2; tìm hiểu cách quản lý dịch vụ bằng systemctl. | 25/08/2026 | 25/08/2026 | [AWS Cloud Journey](https://cloudjourney.awsstudygroup.com/) |
| 4 | Cài đặt PHP, PHP-FPM và các thành phần cần thiết để chạy ứng dụng PHP. | 26/08/2026 | 27/08/2026 | [AWS Cloud Journey](https://cloudjourney.awsstudygroup.com/) |
| 5 | Xây dựng và triển khai giao diện Maiora Fashion Store bằng PHP; tạo các trang sản phẩm và chức năng cơ bản. | 28/08/2026 | 28/08/2026 | [AWS Cloud Journey](https://cloudjourney.awsstudygroup.com/) |
| 6 | Kiểm tra website qua trình duyệt, kiểm tra dịch vụ Apache và xử lý các lỗi phát sinh trong quá trình triển khai. | 29/08/2026 | 29/08/2026 | [AWS Cloud Journey](https://cloudjourney.awsstudygroup.com/) |

### Kết quả đạt được tuần 3:

- Hiểu cách triển khai ứng dụng web trên Amazon EC2 sử dụng hệ điều hành Amazon Linux.

- Làm quen với các thao tác quản trị Linux:
  - Quản lý tệp và thư mục.
  - Kiểm tra và thay đổi quyền truy cập.
  - Sử dụng các lệnh quản trị cơ bản.
  - Kiểm tra trạng thái dịch vụ bằng systemctl.
  - Kiểm tra nhật ký hệ thống và xử lý lỗi cơ bản.

- Cài đặt và cấu hình môi trường máy chủ web:
  - Amazon Linux.
  - Apache HTTP Server.
  - PHP.
  - PHP-FPM.

- Xây dựng và triển khai website thương mại điện tử Maiora Fashion Store:
  - Tạo giao diện trang chủ.
  - Xây dựng trang hiển thị danh sách sản phẩm.
  - Tạo các trang đăng ký và đăng nhập.
  - Xây dựng chức năng giỏ hàng.
  - Xây dựng chức năng đặt hàng và xem đơn hàng.
  - Tổ chức mã nguồn và các thành phần của ứng dụng PHP.

- Cấu hình Security Group để cho phép các kết nối cần thiết:
  - SSH (TCP 22) phục vụ quản trị máy chủ.
  - HTTP (TCP 80) phục vụ truy cập website.
  - HTTPS (TCP 443) khi triển khai chứng chỉ SSL/TLS.

- Kiểm tra hoạt động của máy chủ web:
  - Kiểm tra trạng thái dịch vụ Apache.
  - Kiểm tra PHP và PHP-FPM.
  - Truy cập website thông qua địa chỉ IPv4 công khai của EC2.
  - Kiểm tra khả năng hiển thị giao diện và các chức năng cơ bản.

- Hiểu vai trò của các thành phần trong kiến trúc ứng dụng:
  - Amazon EC2: Cung cấp môi trường chạy ứng dụng.
  - Apache: Tiếp nhận và xử lý các yêu cầu HTTP.
  - PHP: Xử lý logic nghiệp vụ của website.
  - PHP-FPM: Quản lý tiến trình thực thi PHP.

- Hoàn thành việc triển khai phiên bản ban đầu của Maiora Fashion Store trên EC2, tạo nền tảng để tích hợp cơ sở dữ liệu Amazon RDS và lưu trữ hình ảnh sản phẩm trên Amazon S3 trong tuần tiếp theo.
