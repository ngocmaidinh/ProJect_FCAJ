
---
title: "Worklog Tuần 1"
date: 2026-08-10
weight: 1
chapter: false
pre: "<b>1.1.</b>"
---

### Mục tiêu tuần 1:

- Làm quen với các thành viên trong chương trình First Cloud AI Journey (FCAJ).
- Tìm hiểu môi trường thực tập, nội quy và quy trình làm việc.
- Tìm hiểu tổng quan về Amazon Web Services (AWS) và các nhóm dịch vụ điện toán đám mây.
- Làm quen với AWS Management Console và AWS Command Line Interface (AWS CLI).
- Tìm hiểu các dịch vụ AWS có liên quan đến đề tài Backup và Disaster Recovery.
- Xác định phạm vi và các thành phần chính của hệ thống Maiora Fashion Store dự kiến triển khai.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
|---|---|---|---|---|
| 2 | Làm quen với các thành viên FCAJ; tìm hiểu nội quy, môi trường thực tập và quy trình làm việc. | 10/08/2026 | 10/08/2026 | Tài liệu hướng dẫn thực tập |
| 3 | Tìm hiểu tổng quan về AWS và các nhóm dịch vụ Compute, Storage, Networking, Database và Security. | 11/08/2026 | 11/08/2026 | [AWS Cloud Journey](https://cloudjourney.awsstudygroup.com/) |
| 4 | Làm quen với AWS Management Console, AWS CLI, AWS Region và Availability Zone. | 12/08/2026 | 12/08/2026 | [AWS Cloud Journey](https://cloudjourney.awsstudygroup.com/) |
| 5 | Tìm hiểu Amazon EC2, Amazon EBS, AMI, Instance Types, Key Pair và Elastic IP. | 13/08/2026 | 14/08/2026 | [Amazon EC2 Documentation](https://docs.aws.amazon.com/ec2/) |
| 6 | Tìm hiểu IAM, Amazon S3, Amazon RDS, AWS Backup và các khái niệm cơ bản về Backup và Disaster Recovery. | 15/08/2026 | 15/08/2026 | [AWS Documentation](https://docs.aws.amazon.com/) |

### Kết quả đạt được tuần 1:

- Làm quen với các thành viên FCAJ, nắm được nội quy và quy trình làm việc trong chương trình.

- Hiểu tổng quan về Amazon Web Services (AWS) và các nhóm dịch vụ cơ bản:
  - Compute.
  - Storage.
  - Networking.
  - Database.
  - Security.

- Làm quen với các công cụ quản lý AWS:
  - AWS Management Console.
  - AWS Command Line Interface (AWS CLI).
  - AWS Region.
  - Availability Zone.

- Tìm hiểu các dịch vụ AWS liên quan đến đề tài:
  - Amazon EC2: Cung cấp máy chủ ảo để triển khai website.
  - Amazon EBS: Cung cấp ổ lưu trữ cho máy chủ EC2.
  - Amazon RDS: Dịch vụ cơ sở dữ liệu quan hệ được quản lý.
  - Amazon S3: Lưu trữ hình ảnh sản phẩm và dữ liệu đối tượng.
  - AWS Backup: Quản lý và thực hiện sao lưu tài nguyên AWS.
  - IAM: Quản lý danh tính, vai trò và quyền truy cập dịch vụ AWS.

- Nắm được các khái niệm cơ bản:
  - Backup: Sao lưu dữ liệu và tài nguyên hệ thống.
  - Recovery Point: Điểm khôi phục được tạo từ bản sao lưu.
  - Restore: Khôi phục tài nguyên từ bản sao lưu.
  - Disaster Recovery: Khôi phục hệ thống sau khi xảy ra sự cố.
  - RPO (Recovery Point Objective): Mục tiêu điểm khôi phục.
  - RTO (Recovery Time Objective): Mục tiêu thời gian khôi phục.

- Xác định được mô hình ứng dụng dự kiến triển khai là website thương mại điện tử Maiora Fashion Store, sử dụng EC2 làm máy chủ ứng dụng, RDS MySQL làm cơ sở dữ liệu và S3 lưu trữ hình ảnh sản phẩm.

- Bước đầu xác định định hướng kiến trúc hệ thống gồm Region chính Singapore (`ap-southeast-1`) và Region dự phòng Sydney (`ap-southeast-2`), phục vụ việc triển khai cơ chế sao lưu và bảo vệ dữ liệu ở các tuần tiếp theo.
