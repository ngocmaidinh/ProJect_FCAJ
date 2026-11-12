---
title: "Chuẩn bị"
date: 2026-10-29
weight: 2
chapter: false
pre: " <b>4.2.</b> "
---

### 1. Tổng quan về môi trường triển khai

Để triển khai hệ thống Backup và Disaster Recovery cho website Maiora Fashion Store, chúng ta cần chuẩn bị môi trường điện toán đám mây AWS, hạ tầng ứng dụng, cơ sở dữ liệu và các tài nguyên lưu trữ cần thiết.

Môi trường chính được triển khai tại Region Singapore (ap-southeast-1), trong đó website được vận hành trên máy chủ Amazon EC2 và sử dụng Amazon RDS for MySQL để lưu trữ dữ liệu ứng dụng. Amazon S3 được sử dụng để lưu trữ hình ảnh sản phẩm và các tài nguyên của website.

Region Sydney (ap-southeast-2) được sử dụng làm nơi nhận dữ liệu thông qua cơ chế Amazon S3 Cross-Region Replication. Cấu hình này giúp duy trì bản sao hình ảnh sản phẩm tại một AWS Region khác. AWS Backup được sử dụng để quản lý các bản sao lưu và Recovery Point cho những tài nguyên được hỗ trợ, bao gồm Amazon EC2 và Amazon RDS.

### 2. Các thành phần cần chuẩn bị

- **Amazon Web Services (AWS):** Cung cấp hạ tầng điện toán đám mây và các dịch vụ cần thiết để triển khai ứng dụng, lưu trữ dữ liệu và xây dựng cơ chế sao lưu, khôi phục.

- **Amazon VPC:** Cung cấp môi trường mạng riêng biệt để triển khai các tài nguyên ứng dụng và cơ sở dữ liệu. VPC bao gồm Public Subnet, Private Subnet, Route Tables, Internet Gateway và Security Groups.

- **Amazon EC2:** Được sử dụng để triển khai website Maiora Fashion Store bằng PHP và Apache. Máy chủ EC2 đóng vai trò là Application Server và thực hiện kết nối đến cơ sở dữ liệu được lưu trữ trên Amazon RDS.

- **Amazon RDS for MySQL:** Cung cấp dịch vụ cơ sở dữ liệu quan hệ được quản lý, dùng để lưu trữ thông tin website, bao gồm tài khoản khách hàng, thông tin sản phẩm, giỏ hàng và đơn hàng.

- **Amazon S3:** Được sử dụng để lưu trữ hình ảnh sản phẩm và các tài nguyên của website. S3 Versioning giúp lưu giữ các phiên bản của đối tượng, trong khi Cross-Region Replication (CRR) hỗ trợ sao chép dữ liệu từ bucket chính tại Singapore sang bucket đích tại Sydney.

- **AWS Backup:** Cung cấp khả năng quản lý sao lưu tập trung cho các tài nguyên AWS được hỗ trợ, bao gồm Amazon EC2 và Amazon RDS. Backup Vault và Recovery Point được sử dụng để tổ chức, quản lý và khôi phục các tài nguyên đã sao lưu.

- **Máy tính quản trị:** Được sử dụng để truy cập AWS Management Console, cấu hình các tài nguyên AWS, kết nối đến máy chủ EC2, quản lý các tệp ứng dụng và kiểm tra hoạt động của website.

#### Hình ảnh môi trường triển khai

Hình 4.2.1: Môi trường Amazon VPC và hạ tầng ứng dụng tại Region Singapore.

![AWS VPC Environment](/ProJect_FCAJ/images/5-Workshop/5.2-Prerequisite/aws-vpc-environment.png)

Hình 4.2.2: Website Maiora Fashion Store được vận hành trên Amazon EC2.

![Maiora Fashion Store Website](/ProJect_FCAJ/images/5-Workshop/5.2-Prerequisite/maiora-website.png)

Hình 4.2.3: Các bucket Amazon S3 được cấu hình sao chép dữ liệu giữa hai Region.

![Amazon S3 Cross-Region Replication](/ProJect_FCAJ/images/5-Workshop/5.2-Prerequisite/s3-cross-region-replication.png)

Hình 4.2.4: AWS Backup Vault và các Recovery Point.

![AWS Backup Vault](/ProJect_FCAJ/images/5-Workshop/5.2-Prerequisite/aws-backup-vault.png)

### 3. Yêu cầu trước khi triển khai

1. Có tài khoản AWS và quyền truy cập để tạo, quản lý các tài nguyên AWS cần thiết.
2. Lựa chọn Region Singapore (ap-southeast-1) làm Region triển khai chính.
3. Chuẩn bị VPC với Public Subnet, Private Subnet, Route Tables, Internet Gateway và các Security Groups phù hợp.
4. Có máy chủ Amazon EC2 để triển khai website sử dụng PHP.
5. Tạo và cấu hình cơ sở dữ liệu Amazon RDS for MySQL, cho phép máy chủ ứng dụng truy cập.
6. Chuẩn bị Amazon S3 bucket để lưu trữ hình ảnh sản phẩm và kích hoạt tính năng Versioning.
7. Chuẩn bị S3 bucket đích tại Region Sydney (ap-southeast-2) để triển khai Cross-Region Replication.
8. Chuẩn bị quyền AWS Backup và cấu hình sao lưu cần thiết để bảo vệ tài nguyên Amazon EC2 và Amazon RDS.
9. Chuẩn bị các tệp mã nguồn website và cấu hình kết nối cơ sở dữ liệu để triển khai, kiểm tra.
10. Có máy tính quản trị được kết nối Internet và trình duyệt web hiện đại để quản lý các tài nguyên AWS.

#### Kết quả mong đợi

Sau khi hoàn thành bước chuẩn bị, chúng ta sẽ có tài khoản AWS sẵn sàng triển khai, môi trường ứng dụng chính tại Region Singapore và các tài nguyên cơ sở dữ liệu, lưu trữ cần thiết.

Bucket S3 đích tại Region Sydney cùng cấu hình AWS Backup cần thiết sẽ tạo cơ sở để triển khai cơ chế sao chép đối tượng giữa các Region và sao lưu tài nguyên.

Những bước chuẩn bị này là nền tảng để tiếp tục triển khai ứng dụng, cấu hình cơ sở dữ liệu và lưu trữ, quản lý sao lưu và thực hiện các quy trình khôi phục trong những phần tiếp theo.