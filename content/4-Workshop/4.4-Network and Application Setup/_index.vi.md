
---
title: "Cấu hình mạng và triển khai ứng dụng"
date: 2026-10-31
weight: 4
chapter: false
pre: " <b>4.4.</b> "
---

## 1. Tổng quan

Trong phần này, chúng ta sẽ cấu hình hạ tầng mạng trên AWS và triển khai máy chủ ứng dụng cho hệ thống Maiora Fashion Store.

Hạ tầng chính được triển khai tại khu vực Singapore (`ap-southeast-1`). VPC cung cấp môi trường mạng riêng biệt, trong khi EC2 đảm nhiệm việc lưu trữ và vận hành ứng dụng website được xây dựng bằng PHP.

Các nội dung chính bao gồm:

- Tạo và cấu hình Amazon VPC.
- Tạo Public Subnet và Private Subnet.
- Cấu hình Internet Gateway và Route Table.
- Tạo Security Group cho máy chủ ứng dụng.
- Khởi tạo EC2 Instance.
- Cài đặt và cấu hình môi trường Web Server.
- Triển khai và kiểm tra website Maiora Fashion Store.

## 2. Tạo Amazon VPC

Amazon Virtual Private Cloud (Amazon VPC) cho phép xây dựng một mạng ảo riêng biệt trong môi trường AWS.

Trong workshop này, chúng ta tạo VPC có tên `backup-dr-vpc` tại khu vực Singapore.

### 2.1. Thông số cấu hình VPC

Sử dụng các thông số sau:

| Thông số | Giá trị |
|---|---|
| Name | backup-dr-vpc |
| Region | Asia Pacific (Singapore) |
| IPv4 CIDR | 10.0.0.0/16 |
| Availability Zones | 2 |
| Public Subnets | 2 |
| Private Subnets | 2 |
| NAT Gateway | Không cấu hình |
| VPC Endpoints | Không cấu hình |

### 2.2. Tạo VPC

Các bước thực hiện:

1. Truy cập AWS Management Console.
2. Tìm kiếm dịch vụ **VPC**.
3. Chọn **Your VPCs**.
4. Nhấn **Create VPC**.
5. Nhập tên VPC và địa chỉ IPv4 CIDR.
6. Tiến hành tạo VPC.

![Tạo AWS VPC](/ProJect_FCAJ/images/4-Workshop/4.4-Network-and-Application-Setup/create-vpc.png)

## 3. Cấu hình Subnet

Subnet giúp chia mạng VPC thành các phân đoạn mạng nhỏ hơn, hỗ trợ tổ chức và kiểm soát việc truy cập tài nguyên.

Trong workshop này, hệ thống sử dụng Public Subnet cho máy chủ ứng dụng và Private Subnet cho các tài nguyên nội bộ như cơ sở dữ liệu.

### 3.1. Public Subnet

Public Subnet được liên kết với Route Table có tuyến đường định tuyến lưu lượng truy cập Internet thông qua Internet Gateway.

Máy chủ EC2 được triển khai trong Public Subnet để người dùng có thể truy cập website từ Internet.

### 3.2. Private Subnet

Private Subnet được sử dụng cho những tài nguyên không cần cho phép truy cập trực tiếp từ Internet.

Cơ sở dữ liệu Amazon RDS MySQL được triển khai trong Private Subnet nhằm tăng cường bảo mật.

![Cấu hình VPC Subnet](/ProJect_FCAJ/images/4-Workshop/4.4-Network-and-Application-Setup/vpc-subnets.png)

## 4. Cấu hình Internet Gateway và Route Table

### 4.1. Tạo Internet Gateway

Internet Gateway cho phép các tài nguyên trong Public Subnet giao tiếp với Internet.

Các bước thực hiện:

1. Truy cập VPC Console.
2. Chọn **Internet Gateways**.
3. Nhấn **Create internet gateway**.
4. Nhập tên, ví dụ `backup-dr-igw`.
5. Gắn Internet Gateway vào VPC `backup-dr-vpc`.

### 4.2. Cấu hình Public Route Table

Cấu hình Public Route Table với các tuyến đường sau:

| Destination | Target |
|---|---|
| 10.0.0.0/16 | local |
| 0.0.0.0/0 | Internet Gateway |

Sau đó liên kết Route Table với các Public Subnet.

Trong phạm vi workshop này, Private Subnet không được cấu hình tuyến đường trực tiếp đến Internet Gateway.

![Internet Gateway và Route Table](/ProJect_FCAJ/images/4-Workshop/4.4-Network-and-Application-Setup/internet-gateway-route-table.png)

## 5. Tạo Security Group

Security Group hoạt động như một tường lửa ảo, kiểm soát lưu lượng truy cập vào và ra khỏi các tài nguyên AWS.

### 5.1. Security Group cho EC2

Tạo Security Group có tên `ec2-sg` dành cho máy chủ ứng dụng EC2.

Cấu hình các Inbound Rules như sau:

| Type | Protocol | Port | Source |
|---|---|---|---|
| SSH | TCP | 22 | Địa chỉ IP của quản trị viên |
| HTTP | TCP | 80 | 0.0.0.0/0 |
| HTTPS | TCP | 443 | 0.0.0.0/0 |

Đối với SSH, cần giới hạn quyền truy cập trong phạm vi địa chỉ IP đáng tin cậy của quản trị viên.

### 5.2. Security Group cho RDS

Cơ sở dữ liệu RDS sử dụng Security Group riêng có tên `rds-sg`.

Cấu hình Inbound Rule như sau:

| Type | Protocol | Port | Source |
|---|---|---|---|
| MySQL/Aurora | TCP | 3306 | Security Group của EC2 (`ec2-sg`) |

Cấu hình này cho phép máy chủ ứng dụng giao tiếp với cơ sở dữ liệu mà không cần công khai RDS ra Internet.

## 6. Khởi tạo EC2 Application Server

Amazon EC2 cung cấp máy chủ ảo được sử dụng để lưu trữ và vận hành website Maiora Fashion Store.

### 6.1. Thông số cấu hình EC2

Sử dụng cấu hình tham khảo sau:

| Thông số | Giá trị |
|---|---|
| Instance name | app-server |
| Region | Singapore |
| Instance type | t3.micro |
| Operating system | Amazon Linux |
| VPC | backup-dr-vpc |
| Subnet | Public Subnet |
| Auto-assign public IP | Enabled |
| Security Group | ec2-sg |

Lựa chọn hoặc tạo Key Pair phù hợp để phục vụ việc kết nối SSH đến EC2.

### 6.2. Khởi tạo EC2 Instance

Các bước thực hiện:

1. Truy cập EC2 Console.
2. Chọn **Instances**.
3. Nhấn **Launch instances**.
4. Đặt tên Instance là `app-server`.
5. Chọn Amazon Linux AMI.
6. Chọn loại Instance `t3.micro`.
7. Cấu hình VPC và Public Subnet.
8. Gắn Security Group `ec2-sg`.
9. Chọn Key Pair.
10. Nhấn **Launch instances** để khởi tạo.

![Khởi tạo EC2 Instance](/ProJect_FCAJ/images/4-Workshop/4.4-Network-and-Application-Setup/launch-ec2.png)

## 7. Cấu hình môi trường Web Server

Sau khi EC2 Instance khởi chạy thành công, kết nối đến máy chủ thông qua SSH.

Tiến hành cài đặt và khởi chạy Apache Web Server cùng môi trường PHP.

Các lệnh tham khảo dành cho Amazon Linux:

```bash
sudo dnf update -y
sudo dnf install -y httpd php php-fpm php-mysqlnd
sudo systemctl enable httpd
sudo systemctl start httpd
sudo systemctl enable php-fpm
sudo systemctl start php-fpm
```

Kiểm tra trạng thái Apache:

```bash
sudo systemctl status httpd
```

Kiểm tra phiên bản PHP:

```bash
php -v
```

Đảm bảo Web Server hoạt động trước khi triển khai mã nguồn website.

## 8. Triển khai website Maiora Fashion Store

Ứng dụng Maiora Fashion Store được xây dựng bằng PHP và MySQL.

Các tệp mã nguồn được triển khai vào thư mục gốc của Apache:

```bash
/var/www/html
```

Các thành phần chính của ứng dụng bao gồm:

- `index.php`: Trang chủ.
- `products.php`: Danh sách sản phẩm.
- `login.php`: Đăng nhập.
- `register.php`: Đăng ký tài khoản.
- `cart.php`: Giỏ hàng.
- `checkout.php`: Thanh toán đơn hàng.
- `orders.php`: Lịch sử đơn hàng.
- `auth.php`: Xử lý xác thực và phiên đăng nhập.

Thông tin cấu hình kết nối cơ sở dữ liệu được lưu riêng tại:

```bash
/etc/shop/db-config.php
```

Việc lưu tệp cấu hình bên ngoài thư mục công khai của website giúp hạn chế nguy cơ lộ thông tin đăng nhập cơ sở dữ liệu.

Cần đảm bảo mã nguồn ứng dụng và các tệp cấu hình có quyền sở hữu và quyền truy cập phù hợp.

## 9. Kiểm tra hoạt động của ứng dụng

Sau khi triển khai hoàn tất, truy cập website thông qua địa chỉ IPv4 Public hoặc Elastic IP được liên kết với EC2.

Tiến hành kiểm tra các chức năng:

- Trang chủ hiển thị bình thường.
- Danh sách và thông tin sản phẩm được hiển thị.
- Hình ảnh sản phẩm được tải từ Amazon S3.
- Người dùng có thể truy cập trang đăng nhập và đăng ký.
- Giao diện giỏ hàng hoạt động.
- Website có thể truy cập cơ sở dữ liệu thông qua cấu hình ứng dụng.

![Website Maiora Fashion Store](/ProJect_FCAJ/images/4-Workshop/4.4-Network-and-Application-Setup/maiora-website.png)

## 10. Kết quả đạt được

Sau khi hoàn thành phần này, hệ thống có các thành phần:

- Amazon VPC có tên `backup-dr-vpc`.
- Public Subnet và Private Subnet được cấu hình tại Singapore.
- Internet Gateway và Public Route Table.
- Security Group dành cho EC2 Application Server và RDS Database.
- EC2 Instance có tên `app-server`.
- Apache và PHP được cài đặt và khởi chạy.
- Website Maiora Fashion Store được triển khai và có thể truy cập.

Hạ tầng mạng và máy chủ ứng dụng đã sẵn sàng cho phần cấu hình cơ sở dữ liệu và lưu trữ trong mục tiếp theo.
