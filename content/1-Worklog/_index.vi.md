
---
title: "Nhật ký công việc"
date: 2026-08-10
weight: 1
chapter: false
pre: "<b>1.</b>"
---

# Nhật ký công việc thực tập

### Tổng quan

Phần này trình bày nhật ký công việc trong quá trình thực tập, được thực hiện trong 10 tuần, từ ngày 10/08/2026 đến ngày 18/10/2026.

Trong thời gian này, tôi đã nghiên cứu, thiết kế và triển khai hệ thống Backup và Disaster Recovery (DR) trên nền tảng Amazon Web Services (AWS). Dự án sử dụng website thương mại điện tử thời trang Maiora làm ứng dụng thực tế để minh họa quá trình triển khai hạ tầng đám mây, sao lưu dữ liệu và khôi phục hệ thống.

Các công việc được phân chia theo từng tuần, bắt đầu từ việc tìm hiểu AWS và các dịch vụ cơ bản, tiếp theo là triển khai ứng dụng web, cấu hình cơ sở dữ liệu, thiết lập lưu trữ, xây dựng giải pháp sao lưu và thực hiện kiểm thử Disaster Recovery.

Các hoạt động chính trong quá trình thực tập được tổng hợp như sau:

### Nội dung công việc theo tuần

**Tuần 1:** [Làm quen với AWS và các dịch vụ điện toán đám mây cơ bản](1.1-week1/)

Tìm hiểu chương trình thực tập, nội quy làm việc, AWS Management Console, AWS CLI và các dịch vụ cơ bản của AWS.

**Tuần 2:** [Tìm hiểu mạng AWS và hạ tầng Amazon EC2](1.2-week2/)

Nghiên cứu Amazon VPC, CIDR, Public Subnet, Private Subnet, Route Table, Internet Gateway, Security Group, Network ACL và Amazon EC2.

**Tuần 3:** [Thiết lập môi trường Linux và triển khai ứng dụng Web](1.3-week3/)

Chuẩn bị môi trường Amazon Linux, cài đặt và cấu hình Apache, PHP, đồng thời xây dựng phiên bản ban đầu của website thương mại điện tử thời trang Maiora.

**Tuần 4:** [Cấu hình Amazon RDS và cơ sở dữ liệu MySQL](1.4-week4/)

Thiết lập Amazon RDS for MySQL, tạo cơ sở dữ liệu phục vụ ứng dụng và cấu hình kết nối giữa máy chủ EC2 với cơ sở dữ liệu.

**Tuần 5:** [Lưu trữ Amazon S3 và đồng bộ dữ liệu liên vùng](1.5-week5/)

Lưu trữ hình ảnh sản phẩm trên Amazon S3, kích hoạt S3 Versioning và cấu hình Cross-Region Replication (CRR) nhằm bảo vệ dữ liệu hình ảnh giữa các AWS Region.

**Tuần 6:** [Cấu hình AWS Backup và quản lý quá trình sao lưu](1.6-week6/)

Tạo AWS Backup Vault và Backup Plan, cấu hình các tài nguyên cần sao lưu, đồng thời tìm hiểu Backup Job và Recovery Point.

**Tuần 7:** [Thiết lập môi trường chính và môi trường Disaster Recovery](1.7-week7/)

Tìm hiểu và chuẩn bị môi trường chính tại Singapore và môi trường dự phòng tại Sydney nhằm phục vụ quá trình khôi phục hệ thống liên vùng.

**Tuần 8:** [Thực hiện khôi phục dữ liệu và kiểm tra tính toàn vẹn](1.8-week8/)

Thực hiện khôi phục từ các Recovery Point và kiểm tra khả năng hoạt động, tính toàn vẹn của ứng dụng cũng như các tài nguyên cơ sở dữ liệu sau khôi phục.

**Tuần 9:** [Mô phỏng sự cố Disaster Recovery và đánh giá RTO/RPO](1.9-week9/)

Mô phỏng các tình huống máy chủ ứng dụng và dữ liệu gặp sự cố, kiểm tra quy trình khôi phục và đánh giá hiệu quả phục hồi thông qua hai chỉ số Recovery Time Objective (RTO) và Recovery Point Objective (RPO).

**Tuần 10:** [Kiểm thử hệ thống và hoàn thiện báo cáo thực tập](1.10-week10/)

Rà soát cấu hình hệ thống, hoàn thành kiểm thử Backup và Disaster Recovery, thu thập hình ảnh minh chứng trên AWS, tổng hợp kết quả kiểm thử và hoàn thiện báo cáo thực tập.
