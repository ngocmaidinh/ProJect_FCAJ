
---
title: "Worklog Tuần 6"
date: 2026-09-14
weight: 6
chapter: false
pre: "<b>1.6.</b>"
---

### Mục tiêu tuần 6:

- Tìm hiểu AWS Backup và cơ chế quản lý sao lưu tập trung trên AWS.
- Tạo Backup Vault để lưu trữ các điểm khôi phục.
- Cấu hình Backup Plan và Backup Rule cho các tài nguyên cần bảo vệ.
- Thực hiện sao lưu Amazon EC2 và Amazon RDS.
- Kiểm tra trạng thái Backup Job và Recovery Point.
- Tìm hiểu IAM Role và các quyền cần thiết để thực hiện sao lưu và khôi phục tài nguyên.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
|---|---|---|---|---|
| 2 | Tìm hiểu AWS Backup, Backup Vault, Backup Plan, Backup Job và Recovery Point. | 14/09/2026 | 14/09/2026 | [AWS Backup Documentation](https://docs.aws.amazon.com/aws-backup/) |
| 3 | Tạo Backup Vault `BackupDR-Vault` và tìm hiểu cách cấu hình Backup Plan, Backup Rule. | 15/09/2026 | 15/09/2026 | [AWS Backup Documentation](https://docs.aws.amazon.com/aws-backup/) |
| 4 | Lựa chọn và cấu hình các tài nguyên Amazon EC2, Amazon RDS cần được bảo vệ bằng AWS Backup. | 16/09/2026 | 17/09/2026 | [AWS Backup Documentation](https://docs.aws.amazon.com/aws-backup/) |
| 5 | Thực hiện sao lưu thử nghiệm và theo dõi trạng thái Backup Job của EC2 và RDS. | 18/09/2026 | 18/09/2026 | [AWS Backup Documentation](https://docs.aws.amazon.com/aws-backup/) |
| 6 | Kiểm tra Recovery Point, thời gian tạo bản sao lưu, thời gian lưu giữ và các yếu tố ảnh hưởng đến chi phí. | 19/09/2026 | 19/09/2026 | [AWS Backup Documentation](https://docs.aws.amazon.com/aws-backup/) |

### Kết quả đạt được tuần 6:

- Hiểu được AWS Backup và vai trò của dịch vụ trong việc quản lý, tự động hóa và tập trung hóa hoạt động sao lưu tài nguyên AWS.

- Nắm được các thành phần cơ bản của AWS Backup:
  - Backup Plan.
  - Backup Rule.
  - Backup Vault.
  - Recovery Point.
  - Backup Job.
  - Restore Job.

- Thực hiện cấu hình hệ thống sao lưu:
  - Tạo Backup Vault có tên `BackupDR-Vault`.
  - Tìm hiểu và cấu hình Backup Plan.
  - Thiết lập Backup Rule và lịch sao lưu.
  - Cấu hình thời gian lưu giữ bản sao lưu.
  - Lựa chọn tài nguyên cần được bảo vệ.

- Tìm hiểu và thực hiện sao lưu các tài nguyên:
  - Amazon EC2: Sao lưu máy chủ ứng dụng và dữ liệu liên quan thông qua cơ chế bảo vệ EC2.
  - Amazon RDS for MySQL: Sao lưu cơ sở dữ liệu phục vụ website Maiora Fashion Store.
  - Amazon EBS: Tìm hiểu cơ chế bảo vệ dữ liệu ổ đĩa thông qua EC2 Backup hoặc cơ chế sao lưu EBS phù hợp.

- Thực hành theo dõi và kiểm tra kết quả sao lưu:
  - Kiểm tra trạng thái Backup Job.
  - Xác định các tác vụ sao lưu thành công hoặc thất bại.
  - Kiểm tra Recovery Point được tạo trong Backup Vault.
  - Xác định thời điểm tạo bản sao lưu.
  - Kiểm tra thông tin tài nguyên được bảo vệ.

- Tìm hiểu IAM Role và quyền truy cập cần thiết cho AWS Backup:
  - Vai trò của IAM Role trong quá trình sao lưu và khôi phục.
  - Trust Relationship cho phép dịch vụ AWS Backup sử dụng IAM Role.
  - Quyền thực hiện Backup và Restore.
  - Quyền `iam:PassRole` trong quá trình khôi phục tài nguyên khi cần thiết.

- Hiểu cách sử dụng Recovery Point làm cơ sở để khôi phục máy chủ ứng dụng và cơ sở dữ liệu khi xảy ra sự cố.

- Tìm hiểu các yếu tố ảnh hưởng đến chi phí AWS Backup:
  - Dung lượng dữ liệu sao lưu.
  - Thời gian lưu giữ Recovery Point.
  - Số lượng bản sao lưu.
  - Các hoạt động khôi phục và truyền dữ liệu liên quan.

- Hoàn thành việc thiết lập và kiểm tra cơ chế sao lưu tập trung cho các tài nguyên EC2 và RDS, tạo cơ sở cho quá trình thực hiện Disaster Recovery và kiểm thử khôi phục ở các tuần tiếp theo.
