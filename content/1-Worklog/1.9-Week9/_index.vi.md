
---
title: "Worklog Tuần 9"
date: 2026-10-05
weight: 9
chapter: false
pre: "<b>1.9.</b>"
---

### Mục tiêu tuần 9:

- Xây dựng và mô phỏng các tình huống sự cố có thể xảy ra đối với hệ thống Maiora Fashion Store.
- Thực hiện kiểm tra khả năng khôi phục dữ liệu và tài nguyên từ các bản sao lưu.
- Đánh giá khả năng hoạt động của website sau khi khôi phục.
- Ghi nhận thời gian phục hồi và đánh giá các chỉ số Recovery Time Objective (RTO), Recovery Point Objective (RPO).
- Xác định hạn chế và đề xuất cải thiện phương án Backup và Disaster Recovery.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
|---|---|---|---|---|
| 2 | Xây dựng các kịch bản mô phỏng sự cố: mất dữ liệu, xóa nhầm đối tượng S3 và máy chủ ứng dụng EC2 ngừng hoạt động. | 05/10/2026 | 05/10/2026 | [AWS Disaster Recovery](https://docs.aws.amazon.com/whitepapers/latest/disaster-recovery-workloads-on-aws/) |
| 3 | Kiểm tra S3 Versioning, Delete Marker và khả năng khôi phục phiên bản hình ảnh sản phẩm. | 06/10/2026 | 06/10/2026 | [Amazon S3 Versioning](https://docs.aws.amazon.com/AmazonS3/latest/userguide/Versioning.html) |
| 4 | Mô phỏng sự cố máy chủ EC2 và thực hiện khôi phục từ AWS Backup Recovery Point. | 07/10/2026 | 08/10/2026 | [AWS Backup Documentation](https://docs.aws.amazon.com/aws-backup/) |
| 5 | Kiểm tra trạng thái RDS, dữ liệu cơ sở dữ liệu và khả năng hoạt động của website sau khôi phục. | 09/10/2026 | 09/10/2026 | [Amazon RDS Documentation](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/) |
| 6 | Ghi nhận thời gian phục hồi, xác định RTO và đánh giá RPO dựa trên Recovery Point được sử dụng. | 10/10/2026 | 10/10/2026 | [AWS Disaster Recovery](https://docs.aws.amazon.com/whitepapers/latest/disaster-recovery-workloads-on-aws/) |

### Kết quả đạt được tuần 9:

- Xây dựng các kịch bản mô phỏng sự cố cho hệ thống Maiora Fashion Store:
  - Mất hoặc xóa nhầm dữ liệu.
  - Máy chủ ứng dụng Amazon EC2 ngừng hoạt động.
  - Cơ sở dữ liệu Amazon RDS gặp sự cố hoặc cần khôi phục.
  - Hình ảnh sản phẩm trên Amazon S3 bị xóa hoặc sử dụng sai phiên bản.

- Thực hiện kiểm tra quy trình khôi phục tài nguyên bằng AWS Backup:
  - Lựa chọn Recovery Point phù hợp.
  - Kiểm tra trạng thái Backup Job và Recovery Point.
  - Khôi phục máy chủ ứng dụng EC2.
  - Kiểm tra trạng thái tài nguyên sau khi khôi phục.
  - Xác định các cấu hình cần cập nhật để website hoạt động trở lại.

- Kiểm tra khả năng bảo vệ và khôi phục dữ liệu trên Amazon S3:
  - Kiểm tra trạng thái Versioning của bucket.
  - Quan sát các phiên bản đối tượng trong danh sách Show versions.
  - Tìm hiểu cơ chế Delete Marker khi xóa đối tượng.
  - Kiểm tra khả năng khôi phục phiên bản hình ảnh phù hợp.
  - Tìm hiểu hành vi sao chép đối tượng và thao tác xóa giữa bucket Singapore và bucket Sydney thông qua Cross-Region Replication.

- Kiểm tra cơ sở dữ liệu Amazon RDS sau quá trình khôi phục:
  - Kiểm tra trạng thái DB Instance.
  - Xác định endpoint của cơ sở dữ liệu sau khi khôi phục.
  - Kiểm tra dữ liệu phục vụ website Maiora Fashion Store.
  - Xác định các thay đổi cần thiết trong cấu hình kết nối của ứng dụng PHP.

- Đánh giá khả năng hoạt động của website sau khi khôi phục:
  - Kiểm tra khả năng truy cập trang chủ.
  - Kiểm tra danh sách sản phẩm và thông tin sản phẩm.
  - Kiểm tra khả năng tải hình ảnh từ Amazon S3.
  - Kiểm tra các chức năng ứng dụng phù hợp.
  - Xác định các lỗi phát sinh do thay đổi endpoint, địa chỉ IP hoặc cấu hình tài nguyên.

- Tìm hiểu vai trò của Amazon CloudWatch trong việc giám sát tài nguyên:
  - Theo dõi các chỉ số hoạt động của EC2.
  - Quan sát trạng thái và các chỉ số liên quan đến RDS.
  - Tìm hiểu khả năng thiết lập Alarm để phát hiện tình trạng bất thường.
  - Nghiên cứu cách kết hợp CloudWatch với các dịch vụ thông báo khi cần thiết.

- Ghi nhận thời gian phục hồi để đánh giá Recovery Time Objective (RTO):
  - Xác định thời điểm bắt đầu sự cố hoặc thời điểm bắt đầu quy trình khôi phục theo kịch bản kiểm thử.
  - Ghi nhận thời điểm tài nguyên được khôi phục.
  - Xác định thời điểm website hoạt động trở lại và vượt qua các bước kiểm tra cần thiết.
  - Tính tổng thời gian phục hồi dựa trên các mốc thời gian đã ghi nhận.

- Đánh giá Recovery Point Objective (RPO):
  - Xác định thời điểm xảy ra sự cố.
  - Xác định thời điểm của Recovery Point được sử dụng để khôi phục.
  - So sánh hai mốc thời gian để đánh giá khoảng dữ liệu có thể bị mất.
  - Đối chiếu kết quả với mục tiêu RPO dự kiến.

- So sánh kết quả kiểm thử với các mục tiêu RTO/RPO đã xác định, đồng thời đánh giá ảnh hưởng của thời gian lưu giữ bản sao lưu và tần suất sao lưu đến khả năng phục hồi dữ liệu.

- Xác định một số hạn chế của phương án hiện tại:
  - Quá trình khôi phục EC2 và RDS cần thực hiện các bước cấu hình bổ sung.
  - Việc thay đổi endpoint RDS có thể yêu cầu cập nhật cấu hình ứng dụng.
  - Elastic IP có thể cần được gán lại sau khi khôi phục EC2.
  - Dữ liệu S3 được sao chép sang Sydney không đồng nghĩa toàn bộ ứng dụng có thể tự động chuyển sang Region dự phòng.
  - Việc khôi phục tài nguyên có thể phát sinh thêm thời gian và chi phí.

- Đề xuất cải thiện hệ thống:
  - Duy trì Backup Plan và chính sách lưu giữ phù hợp.
  - Kiểm tra Recovery Point định kỳ.
  - Thực hiện kiểm thử khôi phục theo kế hoạch.
  - Xây dựng quy trình cập nhật cấu hình ứng dụng sau khôi phục.
  - Xem xét mở rộng cơ chế giám sát và tự động hóa phục hồi trong tương lai.
