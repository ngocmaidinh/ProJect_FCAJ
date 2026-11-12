
---
title: "Workshop"
date: 2026-11-01
weight: 4
chapter: false
pre: " <b> 4. </b> "
---

# Nghiên cứu và xây dựng hệ thống Backup và Disaster Recovery trên Amazon Web Services (AWS)

### Tổng quan

Trong workshop này, chúng ta sẽ tìm hiểu cách thiết kế và triển khai hệ thống Backup và Disaster Recovery (DR) trên Amazon Web Services (AWS) cho website Maiora Fashion Store.

Hệ thống được triển khai chủ yếu tại Region Singapore (ap-southeast-1), trong đó Amazon EC2 được sử dụng để lưu trữ và vận hành website viết bằng PHP, còn Amazon RDS for MySQL đảm nhiệm việc quản lý dữ liệu ứng dụng, bao gồm tài khoản khách hàng, thông tin sản phẩm, giỏ hàng và đơn hàng. Amazon S3 được sử dụng để lưu trữ hình ảnh sản phẩm và các tài nguyên khác của website.

Để tăng cường khả năng bảo vệ dữ liệu, Amazon S3 Versioning được kích hoạt nhằm lưu giữ nhiều phiên bản khác nhau của đối tượng. Bên cạnh đó, tính năng Cross-Region Replication (CRR) được cấu hình để tự động sao chép hình ảnh sản phẩm từ S3 bucket chính tại Singapore sang bucket đích tại Sydney (ap-southeast-2).

Ngoài ra, AWS Backup được sử dụng làm dịch vụ quản lý sao lưu tập trung cho các tài nguyên được hỗ trợ, bao gồm Amazon EC2 và Amazon RDS. Backup Vault và Recovery Point đóng vai trò quan trọng trong việc quản lý dữ liệu sao lưu, tạo cơ sở để khôi phục hạ tầng ứng dụng và cơ sở dữ liệu khi xảy ra sự cố hoặc mất dữ liệu.

Thông qua workshop này, chúng ta sẽ thực hành chuẩn bị môi trường AWS, triển khai website, cấu hình cơ sở dữ liệu và dịch vụ lưu trữ, xây dựng các cơ chế sao lưu và thực hiện kiểm thử khôi phục nhằm xác minh tính toàn vẹn dữ liệu cũng như khả năng hoạt động của website sau khi khôi phục.

Các nội dung chính bao gồm:

- **Thiết kế kiến trúc AWS:** Xây dựng kiến trúc Backup và Disaster Recovery cho website Maiora Fashion Store bằng các dịch vụ AWS.
- **Triển khai hạ tầng mạng AWS:** Tạo và cấu hình Amazon VPC, Public Subnet, Private Subnet, Route Table, Internet Gateway và Security Groups.
- **Triển khai ứng dụng trên Amazon EC2:** Cài đặt và cấu hình website Maiora Fashion Store sử dụng PHP và Apache trên EC2.
- **Cấu hình cơ sở dữ liệu:** Triển khai Amazon RDS for MySQL và thiết lập kết nối an toàn giữa máy chủ ứng dụng với cơ sở dữ liệu.
- **Lưu trữ và sao chép dữ liệu bằng Amazon S3:** Lưu trữ hình ảnh sản phẩm, kích hoạt S3 Versioning và cấu hình Cross-Region Replication giữa Singapore và Sydney.
- **Quản lý sao lưu bằng AWS Backup:** Tạo Backup Vault, Backup Plan, thiết lập bảo vệ tài nguyên EC2 và RDS, quản lý các Recovery Point.
- **Triển khai Disaster Recovery và khôi phục hệ thống:** Thực hiện các quy trình khôi phục EC2 và RDS, kiểm tra hoạt động của ứng dụng và cơ sở dữ liệu sau khi khôi phục.
- **Kiểm thử hệ thống và dọn dẹp tài nguyên:** Kiểm tra hoạt động sao lưu, khôi phục, xác minh chức năng website và tính toàn vẹn dữ liệu, đồng thời dọn dẹp các tài nguyên AWS khi cần thiết.

### Nội dung

1. [Tổng quan Workshop](4.1-Workshop-overview/)
2. [Chuẩn bị môi trường triển khai](4.2-Prerequisite/)
3. [Thiết kế kiến trúc hệ thống](4.3-Architecture-Design/)
4. [Triển khai hạ tầng mạng AWS](4.4-AWS-Network-Infrastructure/)
5. [Triển khai website Maiora Fashion Store trên Amazon EC2](4.5-EC2-Website-Deployment/)
6. [Cấu hình cơ sở dữ liệu Amazon RDS](4.6-RDS-Database-Configuration/)
7. [Lưu trữ và sao chép dữ liệu bằng Amazon S3](4.7-S3-Storage-Replication/)
8. [Cấu hình và quản lý AWS Backup](4.8-AWS-Backup-Configuration/)
9. [Kiểm thử Disaster Recovery và khôi phục hệ thống](4.9-Disaster-Recovery-Testing/)
10. [Xác minh hệ thống và dọn dẹp tài nguyên AWS](4.10-System-Verification-Cleanup/)
