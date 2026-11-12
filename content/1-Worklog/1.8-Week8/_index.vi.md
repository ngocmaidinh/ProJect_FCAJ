
---
title: "Worklog Tuần 8"
date: 2026-09-28
weight: 8
chapter: false
pre: "<b>1.8.</b>"
---

### Mục tiêu tuần 8:

- Thực hành khôi phục tài nguyên AWS từ bản sao lưu.
- Kiểm tra tính toàn vẹn của dữ liệu sau quá trình khôi phục.
- Đánh giá khả năng phục hồi của website Maiora Fashion Store.
- Xác định các cấu hình bổ sung cần thiết để đưa hệ thống trở lại trạng thái hoạt động.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
|---|---|---|---|---|
| 2 | Kiểm tra Recovery Point của EC2 và RDS, lựa chọn bản sao lưu phù hợp để thử nghiệm khôi phục. | 28/09/2026 | 28/09/2026 | [AWS Cloud Journey](https://cloudjourney.awsstudygroup.com/) |
| 3 | Thực hành khôi phục máy chủ ứng dụng EC2 từ Recovery Point của AWS Backup và kiểm tra cấu hình sau khôi phục. | 29/09/2026 | 29/09/2026 | [AWS Cloud Journey](https://cloudjourney.awsstudygroup.com/) |
| 4 | Thực hành khôi phục cơ sở dữ liệu RDS từ Recovery Point hoặc snapshot phù hợp. | 30/09/2026 | 01/10/2026 | [AWS Cloud Journey](https://cloudjourney.awsstudygroup.com/) |
| 5 | Kiểm tra Amazon S3 Versioning và tìm hiểu cách khôi phục phiên bản đối tượng hình ảnh sản phẩm. | 02/10/2026 | 02/10/2026 | [AWS Cloud Journey](https://cloudjourney.awsstudygroup.com/) |
| 6 | Kiểm tra hoạt động của website, cơ sở dữ liệu và hình ảnh sản phẩm sau khi khôi phục. | 03/10/2026 | 03/10/2026 | [AWS Cloud Journey](https://cloudjourney.awsstudygroup.com/) |

### Kết quả đạt được tuần 8:

- Hiểu được quy trình khôi phục tài nguyên AWS từ Recovery Point và snapshot, bao gồm việc lựa chọn bản sao lưu, khởi tạo quá trình khôi phục và kiểm tra tài nguyên sau khi hoàn thành.

- Thực hành và tìm hiểu quy trình khôi phục máy chủ ứng dụng:
  - Amazon EC2.
  - Amazon EBS.
  - AWS Backup Recovery Point.
  - Kiểm tra trạng thái EC2 sau khi khôi phục.
  - Kiểm tra Security Group, subnet, địa chỉ IP và các cấu hình mạng liên quan.
  - Xác định các cấu hình bổ sung cần thiết để máy chủ có thể tiếp tục phục vụ website.

- Thực hành khôi phục cơ sở dữ liệu:
  - Amazon RDS for MySQL.
  - AWS Backup Recovery Point và RDS Snapshot.
  - Kiểm tra trạng thái cơ sở dữ liệu sau khi khôi phục.
  - Xác định endpoint của RDS được khôi phục.
  - Kiểm tra cấu hình kết nối giữa ứng dụng PHP và cơ sở dữ liệu.
  - Xác định các bước cập nhật cấu hình ứng dụng khi endpoint cơ sở dữ liệu thay đổi.

- Tìm hiểu và kiểm tra cơ chế khôi phục dữ liệu hình ảnh:
  - Amazon S3 Versioning.
  - Các phiên bản đối tượng được lưu trữ trong bucket.
  - Cách khôi phục phiên bản đối tượng phù hợp khi dữ liệu bị ghi đè hoặc xóa.
  - Kiểm tra đường dẫn và khả năng truy cập hình ảnh sau khi khôi phục.
  - Tìm hiểu sự khác biệt giữa Delete Marker và việc xóa vĩnh viễn một phiên bản đối tượng.

- Kiểm tra hoạt động của website Maiora Fashion Store sau quá trình khôi phục:
  - Truy cập trang chủ website.
  - Kiểm tra danh sách và thông tin sản phẩm.
  - Kiểm tra hoạt động của các chức năng ứng dụng phù hợp.
  - Kiểm tra khả năng kết nối cơ sở dữ liệu.
  - Kiểm tra khả năng tải hình ảnh sản phẩm từ Amazon S3.

- Sử dụng AWS Management Console và thông tin trạng thái tài nguyên để xác định các vấn đề phát sinh trong quá trình khôi phục.

- Ghi nhận các cấu hình cần kiểm tra hoặc cập nhật sau khi khôi phục:
  - Endpoint và thông tin kết nối RDS.
  - Security Group và cấu hình mạng.
  - Địa chỉ Elastic IP nếu cần gán lại.
  - Cấu hình ứng dụng PHP.
  - Đường dẫn và quyền truy cập dữ liệu hình ảnh trên S3.

- Hiểu rằng việc khôi phục tài nguyên từ Recovery Point không đảm bảo toàn bộ website tự động hoạt động trở lại. Cần kiểm tra tính tương thích giữa máy chủ ứng dụng, cơ sở dữ liệu, cấu hình mạng và dữ liệu hình ảnh.

- Đánh giá khả năng phục hồi của hệ thống thông qua việc kiểm tra trạng thái tài nguyên và hoạt động của website sau khi khôi phục.
