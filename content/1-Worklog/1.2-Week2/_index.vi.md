
---
title: "Worklog Tuần 2"
date: 2026-08-17
weight: 2
chapter: false
pre: "<b>1.2.</b>"
---

### Mục tiêu tuần 2:

- Tìm hiểu kiến trúc mạng và các thành phần hạ tầng mạng trên AWS.
- Thiết kế và triển khai Amazon VPC phục vụ hệ thống Maiora Fashion Store.
- Cấu hình Public Subnet, Private Subnet, Internet Gateway và Route Table.
- Tìm hiểu cơ chế kiểm soát lưu lượng mạng bằng Security Group và Network ACL.
- Triển khai Amazon EC2 làm máy chủ ứng dụng cho website.
- Kiểm tra khả năng kết nối và truy cập máy chủ EC2.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
|---|---|---|---|---|
| 2 | Tìm hiểu Amazon VPC, CIDR, Availability Zone, Public Subnet, Private Subnet và Route Table. | 17/08/2026 | 17/08/2026 | [AWS Cloud Journey](https://cloudjourney.awsstudygroup.com/) |
| 3 | Tìm hiểu Internet Gateway, Security Group và Network ACL; phân biệt cơ chế kiểm soát lưu lượng mạng. | 18/08/2026 | 18/08/2026 | [AWS Cloud Journey](https://cloudjourney.awsstudygroup.com/) |
| 4 | Thực hành tạo VPC `backup-dr-vpc`, cấu hình CIDR `10.0.0.0/16` và phân chia Public Subnet, Private Subnet. | 19/08/2026 | 20/08/2026 | [AWS Cloud Journey](https://cloudjourney.awsstudygroup.com/) |
| 5 | Cấu hình Internet Gateway, Route Table và Security Group; tạo EC2 làm máy chủ ứng dụng. | 21/08/2026 | 21/08/2026 | [AWS Cloud Journey](https://cloudjourney.awsstudygroup.com/) |
| 6 | Tạo Key Pair, kết nối SSH đến EC2 và kiểm tra trạng thái máy chủ, địa chỉ IP và khả năng truy cập mạng. | 22/08/2026 | 22/08/2026 | [AWS Cloud Journey](https://cloudjourney.awsstudygroup.com/) |

### Kết quả đạt được tuần 2:

- Hiểu kiến trúc mạng trên AWS và vai trò của Amazon VPC trong việc xây dựng môi trường mạng riêng cho hệ thống.

- Nắm được các thành phần mạng cơ bản:
  - Amazon VPC.
  - CIDR Block.
  - Availability Zone.
  - Public Subnet.
  - Private Subnet.
  - Route Table.
  - Internet Gateway.

- Hiểu cơ chế kiểm soát lưu lượng mạng:
  - Security Group: Kiểm soát lưu lượng vào và ra ở cấp độ Elastic Network Interface hoặc EC2 Instance.
  - Network ACL: Kiểm soát lưu lượng vào và ra ở cấp độ Subnet.

- Thiết kế và triển khai VPC cho hệ thống:
  - Tạo VPC có tên `backup-dr-vpc`.
  - Sử dụng dải địa chỉ IP `10.0.0.0/16`.
  - Phân chia hai Public Subnet và hai Private Subnet trên hai Availability Zone.
  - Cấu hình Internet Gateway và Route Table cho các Subnet tương ứng.
  - Không triển khai NAT Gateway và VPC Endpoint trong mô hình thử nghiệm.

- Triển khai và cấu hình Amazon EC2:
  - Lựa chọn Amazon Machine Image (AMI).
  - Sử dụng Instance Type `t3.micro`.
  - Tạo và sử dụng Key Pair.
  - Kết nối SSH đến máy chủ.
  - Kiểm tra trạng thái hoạt động của EC2.

- Tìm hiểu Amazon EBS và vai trò của dịch vụ lưu trữ Block Storage đối với máy chủ EC2.

- Tìm hiểu Elastic IP và cách sử dụng địa chỉ IPv4 công khai để hỗ trợ truy cập máy chủ.

- Hiểu cách kết hợp Amazon VPC, Subnet, Internet Gateway, Route Table và Security Group để xây dựng hạ tầng mạng cho website Maiora Fashion Store.

- Hoàn thành bước chuẩn bị hạ tầng mạng và máy chủ ứng dụng, làm cơ sở cho việc cài đặt môi trường web và triển khai website ở các tuần tiếp theo.
