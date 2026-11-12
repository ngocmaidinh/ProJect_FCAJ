---
title: "Nhật ký thực tập Tuần 9"
date: 2026-10-05
weight: 9
chapter: false
pre: "<b>1.9.</b>"
---

### Mục tiêu tuần 9:

- Xây dựng và tìm hiểu các kịch bản sự cố có thể xảy ra đối với hệ thống Maiora Fashion Store.
- Kiểm thử khả năng khôi phục dữ liệu và tài nguyên từ các bản sao lưu hiện có.
- Kiểm tra chức năng website và tính toàn vẹn dữ liệu sau khi khôi phục.
- Tìm hiểu quy trình phục hồi và xác định các vấn đề có thể phát sinh trong quá trình khôi phục hệ thống.
- Xác định những hạn chế và đề xuất cải tiến cho giải pháp Backup và Disaster Recovery.

### Công việc cần thực hiện trong tuần:

| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
|---|---|---|---|---|
| Thứ Hai | Xây dựng các kịch bản sự cố liên quan đến mất dữ liệu, vô tình xóa đối tượng trên S3 và lỗi máy chủ ứng dụng EC2. | 05/10/2026 | 05/10/2026 | [AWS Cloud Journey](https://cloudjourney.awsstudygroup.com/) |
| Thứ Ba | Kiểm tra S3 Versioning, Delete Marker và khả năng khôi phục các phiên bản hình ảnh sản phẩm. | 06/10/2026 | 06/10/2026 | [AWS Cloud Journey](https://cloudjourney.awsstudygroup.com/) |
| Thứ Tư | Mô phỏng sự cố máy chủ ứng dụng EC2 và khôi phục instance từ AWS Backup Recovery Point. | 07/10/2026 | 08/10/2026 | [AWS Cloud Journey](https://cloudjourney.awsstudygroup.com/) |
| Thứ Sáu | Kiểm tra trạng thái RDS, dữ liệu trong cơ sở dữ liệu và khả năng hoạt động của website sau khi khôi phục. | 09/10/2026 | 09/10/2026 | [AWS Cloud Journey](https://cloudjourney.awsstudygroup.com/) |
| Thứ Bảy | Rà soát quy trình khôi phục, tổng hợp kết quả kiểm thử, xác định hạn chế của hệ thống và đề xuất cải tiến giải pháp Backup và Disaster Recovery. | 10/10/2026 | 10/10/2026 | [AWS Cloud Journey](https://cloudjourney.awsstudygroup.com/) |

### Kết quả đạt được trong tuần 9:

- Xây dựng các kịch bản sự cố có thể xảy ra đối với hệ thống Maiora Fashion Store:
  - Mất dữ liệu hoặc vô tình xóa dữ liệu.
  - Máy chủ ứng dụng Amazon EC2 gặp sự cố.
  - Cơ sở dữ liệu Amazon RDS gặp sự cố hoặc phát sinh nhu cầu khôi phục.
  - Hình ảnh sản phẩm trên Amazon S3 bị xóa hoặc sử dụng sai phiên bản đối tượng.

- Kiểm thử quy trình khôi phục tài nguyên bằng AWS Backup:
  - Lựa chọn Recovery Point phù hợp.
  - Kiểm tra trạng thái Backup Job và Recovery Point.
  - Thực hiện khôi phục máy chủ ứng dụng EC2.
  - Kiểm tra trạng thái tài nguyên sau khi khôi phục.
  - Xác định các thay đổi cấu hình cần thiết để đưa website hoạt động trở lại.

- Tìm hiểu cơ chế bảo vệ và khôi phục dữ liệu trên Amazon S3:
  - Kiểm tra trạng thái Versioning của bucket.
  - Kiểm tra các phiên bản đối tượng thông qua tính năng Show versions.
  - Tìm hiểu cơ chế Delete Marker khi đối tượng bị xóa.
  - Kiểm tra khả năng khôi phục phiên bản hình ảnh sản phẩm phù hợp.
  - Tìm hiểu cơ chế sao chép và hành vi xử lý thao tác xóa giữa bucket Singapore và Sydney thông qua Cross-Region Replication.

- Kiểm tra cơ sở dữ liệu Amazon RDS sau khi khôi phục:
  - Kiểm tra trạng thái DB Instance.
  - Xác định endpoint của cơ sở dữ liệu sau khi khôi phục.
  - Kiểm tra dữ liệu được sử dụng bởi website Maiora Fashion Store.
  - Xác định những thay đổi cần thiết trong cấu hình kết nối cơ sở dữ liệu của ứng dụng PHP.

- Kiểm tra chức năng website sau khi khôi phục:
  - Kiểm tra khả năng truy cập trang chủ.
  - Kiểm tra danh sách và thông tin sản phẩm.
  - Kiểm tra khả năng tải hình ảnh sản phẩm từ Amazon S3.
  - Kiểm tra các chức năng liên quan của ứng dụng.
  - Xác định những vấn đề phát sinh do thay đổi endpoint, địa chỉ IP hoặc cấu hình tài nguyên.

- Tìm hiểu vai trò của Amazon CloudWatch trong giám sát tài nguyên:
  - Tìm hiểu các chỉ số hoạt động của EC2.
  - Kiểm tra trạng thái RDS và các chỉ số liên quan.
  - Tìm hiểu cách sử dụng CloudWatch Alarms để phát hiện các trạng thái bất thường.
  - Tìm hiểu khả năng tích hợp với các dịch vụ thông báo khi cần thiết.

- Rà soát quy trình sao lưu và khôi phục:
  - Kiểm tra các Recovery Point có sẵn để phục vụ quá trình khôi phục tài nguyên.
  - Rà soát các bước khôi phục và cấu hình tài nguyên sau khi phục hồi.
  - Tìm hiểu mối liên hệ giữa tần suất sao lưu, chính sách lưu trữ và khả năng khôi phục dữ liệu.
  - Tổng hợp kết quả kiểm thử khôi phục dựa trên trạng thái tài nguyên và khả năng hoạt động của ứng dụng.

- Xác định một số hạn chế của giải pháp hiện tại:
  - Quá trình khôi phục EC2 và RDS cần thực hiện thêm một số bước cấu hình.
  - Khi endpoint của RDS thay đổi, cần cập nhật lại cấu hình kết nối cơ sở dữ liệu của ứng dụng.
  - Elastic IP có thể cần được gán lại sau khi khôi phục EC2.
  - Việc sao chép dữ liệu S3 sang Sydney không đồng nghĩa với việc ứng dụng tự động chuyển đổi sang Region dự phòng.
  - Quá trình khôi phục tài nguyên có thể cần thêm các bước cấu hình và phát sinh chi phí.

- Đề xuất các hướng cải tiến cho hệ thống:
  - Duy trì Backup Plan và chính sách lưu trữ phù hợp.
  - Kiểm tra Recovery Point định kỳ.
  - Thực hiện kiểm thử khôi phục theo lịch trình.
  - Xây dựng quy trình cập nhật cấu hình ứng dụng sau khi khôi phục.
  - Xem xét mở rộng khả năng giám sát và tự động hóa quy trình khôi phục trong tương lai.