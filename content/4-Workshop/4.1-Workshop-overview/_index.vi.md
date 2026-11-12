---
title: "Giới thiệu"
date: 2026-10-29
weight: 1
chapter: false
pre: " <b>4.1.</b> "
---

### 1. Giới thiệu về hệ thống Backup và Disaster Recovery

- **Backup và Disaster Recovery (DR)** là giải pháp được xây dựng nhằm bảo vệ dữ liệu ứng dụng và duy trì khả năng khôi phục dịch vụ khi xảy ra các sự cố ngoài ý muốn. Việc triển khai các cơ chế sao lưu và khôi phục trên AWS giúp doanh nghiệp giảm thiểu nguy cơ mất dữ liệu và khôi phục các dịch vụ quan trọng khi hệ thống gặp sự cố.

- **Amazon EC2 và Amazon RDS** cung cấp hạ tầng ứng dụng và cơ sở dữ liệu chính cho website Maiora Fashion Store. Amazon EC2 được sử dụng để triển khai ứng dụng website viết bằng PHP, trong khi Amazon RDS for MySQL lưu trữ thông tin tài khoản khách hàng, sản phẩm, giỏ hàng và đơn hàng.

- **Amazon S3** được sử dụng để lưu trữ hình ảnh sản phẩm và các tài nguyên khác của website. S3 Versioning giúp lưu giữ nhiều phiên bản của đối tượng, trong khi Cross-Region Replication (CRR) hỗ trợ sao chép các đối tượng từ bucket chính tại Singapore sang bucket đích tại Sydney.

- **AWS Backup** cung cấp khả năng quản lý sao lưu tập trung đối với các tài nguyên AWS được hỗ trợ, bao gồm Amazon EC2 và Amazon RDS. Thông qua Backup Plan, Backup Vault và Recovery Point, hệ thống có thể tổ chức hoạt động sao lưu và hỗ trợ khôi phục tài nguyên khi cần thiết.

### 2. Tổng quan về Workshop

Trong workshop này, bạn sẽ xây dựng và tìm hiểu giải pháp Backup và Disaster Recovery cho website Maiora Fashion Store bằng cách sử dụng các dịch vụ AWS tại hai Region Singapore và Sydney.

- **"Hạ tầng ứng dụng"** sử dụng Amazon VPC để xây dựng môi trường mạng cho website. Một máy chủ Amazon EC2 được triển khai trong Public Subnet để vận hành ứng dụng PHP, trong khi Amazon RDS for MySQL được đặt trong môi trường mạng riêng nhằm lưu trữ dữ liệu ứng dụng an toàn.

- **"Cấu hình cơ sở dữ liệu và lưu trữ"** sử dụng Amazon RDS for MySQL để quản lý cơ sở dữ liệu website và Amazon S3 để lưu trữ hình ảnh sản phẩm. S3 Versioning được kích hoạt nhằm lưu giữ các phiên bản của đối tượng, đồng thời Cross-Region Replication được cấu hình để sao chép dữ liệu sang bucket tại Region Sydney.

- **"Quản lý sao lưu"** sử dụng AWS Backup để tạo và quản lý Backup Plan, Backup Vault và Recovery Point cho Amazon EC2 và Amazon RDS. Các bản sao lưu này cung cấp phương án khôi phục khi tài nguyên ứng dụng hoặc cơ sở dữ liệu bị hư hỏng hay mất dữ liệu.

- **"Disaster Recovery và khôi phục hệ thống"** tập trung vào việc khôi phục tài nguyên AWS từ các Recovery Point hiện có và kiểm tra hoạt động của website sau khi khôi phục. Workshop cũng tìm hiểu vai trò của cơ chế sao chép đối tượng S3 trong việc bảo vệ hình ảnh sản phẩm giữa các Region.

Thông qua workshop này, bạn sẽ thực hành triển khai hạ tầng ứng dụng trên AWS, cấu hình cơ sở dữ liệu và lưu trữ đối tượng, xây dựng cơ chế sao lưu, thiết lập sao chép dữ liệu giữa các Region và thực hiện các quy trình khôi phục nhằm nâng cao khả năng bảo vệ dữ liệu và phục hồi hoạt động của website Maiora Fashion Store.