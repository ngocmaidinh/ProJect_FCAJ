
---
title: "Worklog Tuần 7"
date: 2026-09-21
weight: 7
chapter: false
pre: "<b>1.7.</b>"
---

### Mục tiêu tuần 7:

- Tìm hiểu kiến trúc Backup và Disaster Recovery trên nhiều AWS Region.
- Phân tích phương án dự phòng giữa Singapore và Sydney.
- Tìm hiểu các cơ chế sao chép dữ liệu và khôi phục tài nguyên giữa các Region.
- Xác định phạm vi dự phòng phù hợp với hệ thống Maiora Fashion Store.
- Xây dựng sơ đồ kiến trúc Backup và Disaster Recovery cho hệ thống.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
|---|---|---|---|---|
| 2 | Tìm hiểu Recovery Time Objective (RTO), Recovery Point Objective (RPO) và các mô hình Disaster Recovery. | 21/09/2026 | 21/09/2026 | [AWS Disaster Recovery](https://docs.aws.amazon.com/whitepapers/latest/disaster-recovery-workloads-on-aws/) |
| 3 | Phân tích kiến trúc hệ thống với Singapore là Region chính và Sydney là Region dự phòng. | 22/09/2026 | 22/09/2026 | [AWS Global Infrastructure](https://aws.amazon.com/about-aws/global-infrastructure/) |
| 4 | Tìm hiểu AWS Backup Cross-Region Copy và Amazon S3 Cross-Region Replication. | 23/09/2026 | 24/09/2026 | [AWS Backup Documentation](https://docs.aws.amazon.com/aws-backup/); [Amazon S3 Replication](https://docs.aws.amazon.com/AmazonS3/latest/userguide/replication.html) |
| 5 | Nghiên cứu phương án khôi phục EC2, RDS và dữ liệu S3 khi Region chính gặp sự cố. | 25/09/2026 | 25/09/2026 | [AWS Disaster Recovery](https://docs.aws.amazon.com/whitepapers/latest/disaster-recovery-workloads-on-aws/) |
| 6 | Xây dựng sơ đồ kiến trúc Backup và DR, xác định quy trình khôi phục hệ thống. | 26/09/2026 | 26/09/2026 | [AWS Architecture Center](https://aws.amazon.com/architecture/) |

### Kết quả đạt được tuần 7:

- Hiểu được kiến trúc Backup và Disaster Recovery triển khai trên nhiều AWS Region, giúp tăng khả năng bảo vệ dữ liệu khi Region chính gặp sự cố.

- Tìm hiểu và xác định vai trò của hai Region trong kiến trúc:
  - Singapore (`ap-southeast-1`): Region chính, triển khai website Maiora Fashion Store, máy chủ ứng dụng EC2 và cơ sở dữ liệu Amazon RDS for MySQL.
  - Sydney (`ap-southeast-2`): Region dự phòng, tiếp nhận dữ liệu hình ảnh sản phẩm được sao chép từ S3 tại Singapore thông qua Cross-Region Replication.

- Tìm hiểu các cơ chế sao chép và bảo vệ dữ liệu giữa các Region:
  - AWS Backup Cross-Region Copy: Sao chép Recovery Point sang Backup Vault tại Region khác khi được cấu hình.
  - Amazon S3 Cross-Region Replication (CRR): Tự động sao chép các đối tượng S3 đáp ứng điều kiện của quy tắc replication sang bucket tại Region đích.
  - Recovery Point: Lưu trữ trạng thái dữ liệu tại một thời điểm nhất định, làm cơ sở cho quá trình khôi phục tài nguyên.

- Nắm được các yêu cầu khi triển khai sao lưu liên Region:
  - Tạo Backup Vault tại Region đích khi sử dụng AWS Backup Cross-Region Copy.
  - Cấu hình IAM Role và quyền truy cập phù hợp.
  - Thiết lập chính sách lưu giữ Recovery Point.
  - Đảm bảo dịch vụ và tài nguyên tại Region đích đáp ứng điều kiện khôi phục.
  - Kiểm tra trạng thái sao chép và khả năng truy cập dữ liệu tại Region đích.

- Tìm hiểu các dịch vụ hỗ trợ tính sẵn sàng và giám sát hệ thống:
  - Amazon Route 53: Quản lý DNS và hỗ trợ định tuyến lưu lượng giữa các endpoint.
  - Amazon CloudWatch: Thu thập và theo dõi các chỉ số hoạt động của tài nguyên AWS.
  - Amazon SNS: Hỗ trợ gửi thông báo khi có sự kiện hoặc cảnh báo.
  - AWS Elastic Disaster Recovery: Hỗ trợ phục hồi máy chủ trên AWS khi xảy ra sự cố.

- Phân tích phương án khôi phục các thành phần của Maiora Fashion Store:
  - EC2: Sử dụng Recovery Point của AWS Backup để khôi phục máy chủ ứng dụng tại Region phù hợp.
  - RDS: Sử dụng bản sao lưu hoặc snapshot phù hợp để khôi phục cơ sở dữ liệu.
  - S3: Sử dụng dữ liệu đã được sao chép sang bucket tại Sydney để hỗ trợ truy cập và khôi phục hình ảnh sản phẩm.

- Xác định quy trình khôi phục tổng quát khi Region chính gặp sự cố:
  - Xác định phạm vi và mức độ ảnh hưởng của sự cố.
  - Lựa chọn Recovery Point phù hợp.
  - Khôi phục máy chủ ứng dụng và cơ sở dữ liệu.
  - Kiểm tra dữ liệu hình ảnh tại Region dự phòng.
  - Cập nhật cấu hình kết nối và địa chỉ truy cập nếu cần thiết.
  - Kiểm tra hoạt động của website sau khi khôi phục.

- Xây dựng sơ đồ kiến trúc Backup và Disaster Recovery cho website Maiora Fashion Store, thể hiện luồng dữ liệu giữa EC2, RDS, S3 và AWS Backup tại Region chính, cùng cơ chế sao chép dữ liệu hình ảnh sang Region dự phòng.

- Hiểu mối quan hệ giữa chi phí triển khai, Recovery Time Objective (RTO) và Recovery Point Objective (RPO). Nhận thấy việc duy trì tài nguyên dự phòng hoạt động liên tục có thể làm tăng chi phí, trong khi phương án khôi phục theo yêu cầu giúp tiết kiệm chi phí nhưng cần thêm thời gian phục hồi.

- Xác định phạm vi triển khai thực tế của đề tài: sử dụng AWS Backup để bảo vệ EC2 và RDS tại Singapore, kết hợp S3 Cross-Region Replication để sao chép dữ liệu hình ảnh sang Sydney. Việc khôi phục EC2 và RDS tại Region khác được xem là phương án DR cần thực hiện theo quy trình khôi phục, không phải cơ chế tự động chuyển đổi dự phòng.
