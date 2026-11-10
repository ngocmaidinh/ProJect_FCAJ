---
title: "Bản đề xuất"
date: 2026-10-17
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

# HỆ THỐNG BACKUP & DISASTER RECOVERY ĐA VÙNG TRÊN AWS
## Giải pháp sao lưu, khôi phục dữ liệu liên vùng và giám sát sự cố

# AWS MULTI-REGION BACKUP & DISASTER RECOVERY SYSTEM
## A Solution for Data Backup, Cross-Region Recovery, and Incident Monitoring

---


## 1. Tóm tắt điều hành

Đề tài tập trung nghiên cứu và xây dựng hệ thống Backup và Disaster Recovery (BDR) đa vùng trên nền tảng Amazon Web Services (AWS), nhằm nâng cao khả năng bảo vệ dữ liệu và duy trì hoạt động của ứng dụng web khi xảy ra sự cố tại môi trường triển khai chính.

Hệ thống được xây dựng dựa trên ứng dụng thương mại điện tử thời trang Maiora, sử dụng PHP để phát triển ứng dụng web, Amazon EC2 để triển khai máy chủ ứng dụng, Amazon RDS để quản lý cơ sở dữ liệu MySQL và Amazon S3 để lưu trữ hình ảnh sản phẩm.

Kiến trúc sử dụng hai AWS Region: Singapore (ap-southeast-1) làm vùng chính và Sydney (ap-southeast-2) làm vùng dự phòng.

Giải pháp kết hợp các dịch vụ AWS nhằm thực hiện ba nhiệm vụ chính: bảo vệ dữ liệu thông qua AWS Backup và Amazon S3 Versioning; sao chép dữ liệu liên vùng bằng S3 Cross-Region Replication; giám sát tình trạng hoạt động và gửi cảnh báo sự cố thông qua Amazon Route 53, Amazon CloudWatch và Amazon SNS.

Đề tài tập trung đánh giá khả năng sao lưu, khôi phục tài nguyên, tính toàn vẹn dữ liệu, khả năng đồng bộ liên vùng và hiệu quả giám sát, cảnh báo sự cố. Thông qua các kịch bản kiểm thử thực tế, hệ thống được đánh giá dựa trên khả năng khôi phục và duy trì hoạt động của website tại môi trường dự phòng.

Kết quả hướng đến là một mô hình BDR đa vùng có thể triển khai và kiểm chứng thực tế, đồng thời xây dựng bộ tài liệu hướng dẫn thực hành có thể tham khảo và áp dụng cho các hệ thống website quy mô nhỏ và vừa.

## 2. Tuyên bố vấn đề

### 2.1. Vấn đề hiện tại

Các ứng dụng web được triển khai tập trung tại một AWS Region có thể gặp rủi ro khi vùng triển khai chính xảy ra sự cố. Khi đó, máy chủ ứng dụng, cơ sở dữ liệu hoặc dữ liệu lưu trữ có thể bị gián đoạn, ảnh hưởng đến khả năng truy cập website và hoạt động của hệ thống.

Bên cạnh đó, nếu chỉ sử dụng phương pháp sao lưu đơn lẻ mà không có phương án khôi phục tại vùng khác, việc phục hồi hệ thống sau sự cố sẽ gặp nhiều khó khăn. Dữ liệu có thể bị mất, sai lệch hoặc không thể truy cập nếu quá trình sao lưu và khôi phục chưa được kiểm chứng.

Đối với các website thương mại điện tử, việc bảo vệ dữ liệu khách hàng, thông tin sản phẩm, đơn hàng và hình ảnh sản phẩm là yêu cầu quan trọng nhằm duy trì hoạt động kinh doanh.

### 2.2. Giải pháp

Đề tài xây dựng hệ thống BDR đa vùng trên AWS, tập trung giải quyết các vấn đề thông qua những phương án sau:

- Sử dụng AWS Backup để quản lý và thực hiện sao lưu các tài nguyên AWS quan trọng, bao gồm máy chủ EC2 và cơ sở dữ liệu RDS.
- Sử dụng Amazon S3 Versioning để lưu giữ các phiên bản khác nhau của đối tượng, hỗ trợ khôi phục khi dữ liệu bị ghi đè hoặc xóa nhầm.
- Sử dụng S3 Cross-Region Replication (CRR) để sao chép dữ liệu hình ảnh sản phẩm từ Singapore sang Sydney.
- Xây dựng môi trường dự phòng tại Sydney, hỗ trợ khôi phục máy chủ ứng dụng và cơ sở dữ liệu từ các bản sao lưu.
- Sử dụng Amazon Route 53 Health Check để kiểm tra tình trạng truy cập website.
- Kết hợp Amazon CloudWatch và Amazon SNS để theo dõi trạng thái giám sát và gửi email cảnh báo khi phát hiện sự cố.

### 2.3. Lợi ích

- Hạn chế nguy cơ mất dữ liệu khi xảy ra sự cố tại vùng triển khai chính.
- Hỗ trợ khôi phục máy chủ, cơ sở dữ liệu và dữ liệu hình ảnh sản phẩm từ các bản sao lưu.
- Tăng khả năng bảo vệ dữ liệu thông qua cơ chế quản lý phiên bản và sao chép liên vùng.
- Có môi trường dự phòng để kiểm tra khả năng duy trì hoạt động của website.
- Phát hiện và thông báo sự cố thông qua hệ thống giám sát và cảnh báo.
- Xây dựng quy trình triển khai, sao lưu, khôi phục và kiểm thử có thể tái sử dụng.

## 3. Kiến trúc giải pháp

Kiến trúc giải pháp được xây dựng theo mô hình hai AWS Region. Singapore là vùng triển khai chính, nơi website Maiora hoạt động và kết nối với cơ sở dữ liệu. Sydney là vùng dự phòng, lưu giữ các bản sao dữ liệu và hỗ trợ khôi phục hệ thống khi cần thiết.

Hệ thống không triển khai cơ chế tự động chuyển đổi toàn bộ dịch vụ giữa hai vùng. Việc khôi phục tại Sydney được thực hiện theo quy trình có kiểm soát, sử dụng các bản sao lưu và dữ liệu đã được sao chép.

![Kiến trúc BDR hai vùng]( /images/2-Proposal/bdr_architecture.png )

### 3.1. Các dịch vụ AWS sử dụng

- **Amazon VPC:** Xây dựng mạng riêng `backup-dr-vpc`, phân chia các subnet công khai và riêng tư để tổ chức tài nguyên ứng dụng và cơ sở dữ liệu.
- **Amazon EC2:** Triển khai máy chủ `app-server` chạy website Maiora bằng PHP và Apache. Elastic IP được sử dụng để duy trì địa chỉ IPv4 công khai của máy chủ chính.
- **Amazon RDS:** Quản lý cơ sở dữ liệu MySQL `backup-dr-db`, lưu trữ thông tin người dùng, sản phẩm, giỏ hàng và đơn hàng. Cơ sở dữ liệu không cho phép truy cập công khai trực tiếp.
- **Amazon S3:** Lưu trữ hình ảnh sản phẩm của website. Bật Versioning để quản lý các phiên bản đối tượng và sử dụng Cross-Region Replication để sao chép dữ liệu sang bucket tại Sydney.
- **AWS Backup:** Quản lý các bản sao lưu tập trung thông qua Backup Vault và Backup Plan, hỗ trợ sao lưu và khôi phục các tài nguyên được cấu hình.
- **Amazon Route 53:** Sử dụng Health Check để kiểm tra tình trạng truy cập website tại vùng chính.
- **Amazon CloudWatch:** Theo dõi trạng thái Health Check và các chỉ số giám sát của tài nguyên, đồng thời thiết lập cảnh báo khi phát hiện trạng thái bất thường.
- **Amazon SNS:** Gửi email thông báo đến quản trị viên khi CloudWatch Alarm chuyển sang trạng thái cảnh báo.
- **AWS IAM:** Quản lý quyền truy cập thông qua người dùng, nhóm quyền và vai trò dịch vụ, bảo đảm các thao tác sao lưu và khôi phục được thực hiện đúng quyền hạn.

### 3.2. Thiết kế các thành phần

- **Ứng dụng web:** Website Maiora được triển khai trên EC2 tại Singapore. Người dùng truy cập website thông qua địa chỉ IP công khai hoặc tên miền đã cấu hình.
- **Cơ sở dữ liệu:** EC2 kết nối đến RDS MySQL thông qua mạng nội bộ, sử dụng Security Group để giới hạn quyền truy cập.
- **Bảo vệ dữ liệu:** AWS Backup thực hiện sao lưu các tài nguyên được chỉ định. Amazon S3 Versioning hỗ trợ khôi phục phiên bản hình ảnh trước đó khi cần thiết.
- **Sao chép liên vùng:** S3 CRR sao chép đối tượng từ bucket tại Singapore sang bucket tại Sydney.
- **Khôi phục hệ thống:** Khi xảy ra sự cố, quản trị viên sử dụng các Recovery Point của AWS Backup để khôi phục tài nguyên tại môi trường dự phòng.
- **Giám sát:** Route 53 Health Check kiểm tra tình trạng website, CloudWatch tiếp nhận và đánh giá trạng thái giám sát.
- **Cảnh báo:** SNS gửi email đến quản trị viên khi phát hiện sự cố thông qua CloudWatch Alarm.

## 4. Triển khai kỹ thuật

### 4.1. Các giai đoạn triển khai

Dự án được triển khai theo các giai đoạn, mỗi giai đoạn có kết quả cụ thể và được kiểm chứng thông qua AWS Management Console, giao diện website hoặc các lệnh kiểm tra cần thiết.

**Giai đoạn 1: Xây dựng nền tảng và quản lý quyền truy cập**

- Tìm hiểu môi trường AWS và các dịch vụ cần thiết.
- Tạo và cấu hình IAM User, IAM Group và các quyền truy cập.
- Thiết lập vai trò dịch vụ phục vụ AWS Backup.
- Xây dựng VPC, subnet, Internet Gateway, Route Table và Security Group.

**Giai đoạn 2: Triển khai ứng dụng và cơ sở dữ liệu tại Singapore**

- Tạo EC2 instance làm máy chủ ứng dụng.
- Cài đặt môi trường Apache, PHP và các thành phần cần thiết.
- Triển khai website thương mại điện tử Maiora.
- Tạo cơ sở dữ liệu MySQL trên Amazon RDS.
- Cấu hình kết nối giữa EC2 và RDS thông qua mạng nội bộ.
- Kiểm tra các chức năng đăng ký, đăng nhập, quản lý sản phẩm, giỏ hàng và đặt hàng.

**Giai đoạn 3: Triển khai lưu trữ và bảo vệ dữ liệu trên S3**

- Tạo S3 Bucket lưu trữ hình ảnh sản phẩm.
- Cấu hình Versioning và mã hóa dữ liệu.
- Thiết lập Cross-Region Replication giữa Singapore và Sydney.
- Kiểm tra khả năng sao chép đối tượng giữa hai bucket.
- Kiểm tra khả năng khôi phục phiên bản đối tượng khi xảy ra thao tác xóa hoặc ghi đè.

**Giai đoạn 4: Xây dựng môi trường dự phòng tại Sydney**

- Chuẩn bị môi trường AWS tại Sydney.
- Triển khai hoặc khôi phục máy chủ ứng dụng từ bản sao lưu.
- Khôi phục cơ sở dữ liệu từ bản sao lưu phù hợp.
- Kiểm tra khả năng kết nối giữa ứng dụng và cơ sở dữ liệu sau khôi phục.
- Kiểm tra khả năng truy cập hình ảnh sản phẩm từ bucket dự phòng.
- Đối chiếu dữ liệu giữa môi trường chính và môi trường dự phòng.

**Giai đoạn 5: Triển khai hệ thống sao lưu bằng AWS Backup**

- Tạo Backup Vault `BackupDR-Vault`.
- Cấu hình Backup Plan cho các tài nguyên cần bảo vệ.
- Gán các tài nguyên EC2 và RDS vào chính sách sao lưu.
- Thực hiện và theo dõi các Backup Job.
- Kiểm tra Recovery Point sau khi sao lưu hoàn tất.
- Thực hiện khôi phục thử nghiệm để kiểm chứng khả năng sử dụng của bản sao lưu.

**Giai đoạn 6: Triển khai giám sát và cảnh báo**

- Tạo Route 53 Health Check để kiểm tra website.
- Cấu hình CloudWatch Alarm theo dõi trạng thái Health Check.
- Thiết lập các cảnh báo giám sát phù hợp cho EC2 và RDS.
- Tạo SNS Topic `BackupDR-Alerts-Route53`.
- Đăng ký email nhận thông báo.
- Kiểm tra email cảnh báo khi phát sinh sự cố.

**Giai đoạn 7: Kiểm thử và đánh giá hệ thống**

- Kiểm thử khả năng sao lưu EC2 và RDS bằng AWS Backup.
- Kiểm thử khôi phục máy chủ ứng dụng từ Recovery Point.
- Kiểm thử khôi phục cơ sở dữ liệu và đối chiếu dữ liệu sau khôi phục.
- Kiểm thử khả năng khôi phục các phiên bản đối tượng trên S3.
- Kiểm tra dữ liệu được sao chép sang Sydney.
- Mô phỏng tình huống máy chủ ứng dụng ngừng hoạt động.
- Kiểm tra khả năng truy cập website tại môi trường dự phòng.
- Kiểm tra khả năng phát hiện sự cố và gửi email cảnh báo.
- Tổng hợp kết quả kiểm thử, ảnh chụp màn hình và các vấn đề phát sinh.

### 4.2. Yêu cầu kỹ thuật

- Có tài khoản AWS và quyền truy cập cần thiết để tạo, cấu hình và quản lý các dịch vụ.
- Sử dụng hai AWS Region: Singapore (ap-southeast-1) và Sydney (ap-southeast-2).
- Sử dụng AWS Management Console làm công cụ triển khai chính, kết hợp AWS CLI khi cần thiết.
- Có kiến thức cơ bản về mạng máy tính, Linux, EC2, RDS, S3, IAM và các dịch vụ giám sát AWS.
- Có khả năng triển khai và kiểm tra ứng dụng web PHP kết nối cơ sở dữ liệu MySQL.

## 5. Lộ trình và mốc triển khai

Dự án được thực hiện theo từng giai đoạn, kết hợp triển khai lý thuyết với thực hành trực tiếp trên AWS.

- **Giai đoạn 1:** Hoàn thành nghiên cứu nền tảng AWS, cấu hình IAM và xây dựng mạng VPC.
- **Giai đoạn 2:** Hoàn thành triển khai EC2, RDS và website Maiora tại Singapore.
- **Giai đoạn 3:** Hoàn thành cấu hình S3, Versioning và Cross-Region Replication.
- **Giai đoạn 4:** Triển khai môi trường dự phòng tại Sydney và kiểm tra khôi phục tài nguyên.
- **Giai đoạn 5:** Hoàn thành cấu hình AWS Backup, Backup Vault, Backup Plan và kiểm tra Recovery Point.
- **Giai đoạn 6:** Triển khai Route 53 Health Check, CloudWatch Alarm và SNS Email Notification.
- **Giai đoạn 7:** Thực hiện các kịch bản kiểm thử, đánh giá kết quả và hoàn thiện tài liệu.

Kết quả triển khai được ghi nhận thông qua ảnh chụp màn hình AWS Console, trạng thái tài nguyên, kết quả kiểm tra website và dữ liệu sau khôi phục.

## 6. Ước tính ngân sách

Chi phí triển khai hệ thống phụ thuộc vào loại tài nguyên, thời gian sử dụng, dung lượng dữ liệu lưu trữ và lượng dữ liệu truyền giữa các AWS Region.

Để phù hợp với mục tiêu nghiên cứu và thực hành, đề tài ưu tiên sử dụng tài nguyên có cấu hình phù hợp, chỉ duy trì những dịch vụ cần thiết cho quá trình triển khai và kiểm thử. Không yêu cầu duy trì toàn bộ môi trường dự phòng hoạt động liên tục.

### 6.1. Các yếu tố phát sinh chi phí

- **Amazon EC2:** Chi phí theo thời gian chạy instance, dung lượng ổ đĩa EBS và các tài nguyên mạng liên quan.
- **Amazon RDS:** Chi phí theo thời gian chạy DB instance, dung lượng lưu trữ và các bản sao lưu vượt mức miễn phí được áp dụng.
- **Amazon S3:** Chi phí lưu trữ dữ liệu, số lượng yêu cầu PUT, GET, COPY và các yêu cầu liên quan đến Versioning, Replication.
- **Truyền dữ liệu liên vùng:** Chi phí phát sinh khi sao chép dữ liệu giữa Singapore và Sydney.
- **AWS Backup:** Chi phí lưu trữ các Recovery Point và các hoạt động liên quan theo chính sách giá của dịch vụ.
- **Amazon Route 53:** Chi phí liên quan đến Health Check.
- **Amazon CloudWatch:** Chi phí cho các Alarm, Metric và hoạt động giám sát theo cấu hình.
- **Amazon SNS:** Chi phí thông báo tùy thuộc vào loại thông báo và số lượng thông báo gửi đi.

### 6.2. Biện pháp kiểm soát chi phí

- Ưu tiên sử dụng EC2 instance có cấu hình phù hợp với ứng dụng thử nghiệm.
- Chỉ khởi chạy môi trường dự phòng khi cần kiểm thử hoặc trình diễn.
- Dừng hoặc xóa EC2 instance không sử dụng sau khi hoàn thành kiểm thử.
- Không duy trì RDS tại hai vùng hoạt động liên tục nếu không cần thiết.
- Thiết lập thời gian lưu giữ bản sao lưu phù hợp với mục tiêu của đề tài.
- Sử dụng S3 Lifecycle để chuyển dữ liệu phù hợp sang các lớp lưu trữ có chi phí thấp hơn.
- Xóa các tài nguyên thử nghiệm không còn sử dụng, đồng thời kiểm tra snapshot, Recovery Point và Elastic IP còn tồn tại.
- Theo dõi chi phí thông qua AWS Billing và Cost Explorer.
- Thiết lập AWS Budgets để nhận cảnh báo khi chi phí vượt ngưỡng dự kiến.

## 7. Đánh giá rủi ro

### 7.1. Ma trận rủi ro

- **Chi phí vượt dự kiến:** Có thể xảy ra khi EC2, RDS hoặc các tài nguyên lưu trữ được duy trì trong thời gian dài. Mức độ ảnh hưởng: trung bình; khả năng xảy ra: trung bình.
- **Bản sao dữ liệu chưa được cập nhật:** Có thể xảy ra khi S3 Replication gặp lỗi hoặc quá trình sao chép chưa hoàn tất. Mức độ ảnh hưởng: cao; khả năng xảy ra: trung bình.
- **Khôi phục tài nguyên không thành công:** Có thể xảy ra do cấu hình IAM, quyền AWS Backup hoặc thông số khôi phục chưa chính xác. Mức độ ảnh hưởng: cao; khả năng xảy ra: trung bình.
- **Dữ liệu sau khôi phục không đầy đủ:** Có thể xảy ra khi bản sao lưu không chứa dữ liệu cần thiết hoặc quá trình khôi phục chưa hoàn tất. Mức độ ảnh hưởng: cao; khả năng xảy ra: trung bình.
- **Cảnh báo không hoạt động:** Có thể xảy ra khi cấu hình Health Check, CloudWatch Alarm hoặc SNS chưa chính xác. Mức độ ảnh hưởng: trung bình; khả năng xảy ra: thấp.
- **Website không hoạt động tại vùng dự phòng:** Có thể xảy ra do sai cấu hình máy chủ, cơ sở dữ liệu, địa chỉ IP hoặc kết nối mạng. Mức độ ảnh hưởng: cao; khả năng xảy ra: trung bình.

### 7.2. Chiến lược giảm thiểu

- **Kiểm soát chi phí:** Theo dõi Billing, sử dụng AWS Budgets và dừng các tài nguyên không cần thiết.
- **Kiểm soát dữ liệu:** Kiểm tra trạng thái S3 Replication, Versioning và đối chiếu dữ liệu giữa hai vùng.
- **Kiểm soát sao lưu:** Theo dõi Backup Job, xác nhận Recovery Point và kiểm tra trạng thái các bản sao lưu.
- **Kiểm soát khôi phục:** Kiểm tra IAM Role, quyền IAM và cấu hình tài nguyên trước khi thực hiện khôi phục.
- **Kiểm soát ứng dụng:** Kiểm tra kết nối cơ sở dữ liệu, cấu hình website và khả năng tải hình ảnh sau khôi phục.
- **Kiểm soát cảnh báo:** Kiểm tra trạng thái Health Check, CloudWatch Alarm và email nhận thông báo.

### 7.3. Kế hoạch dự phòng

- Nếu không thể khôi phục trực tiếp từ AWS Backup, sử dụng bản sao lưu phù hợp khác để phục hồi tài nguyên.
- Nếu dữ liệu S3 chưa được sao chép hoàn chỉnh, kiểm tra trạng thái Replication và sử dụng phiên bản dữ liệu có sẵn.
- Nếu website tại Sydney không hoạt động, kiểm tra lần lượt EC2, cấu hình ứng dụng, cơ sở dữ liệu và kết nối mạng.
- Nếu quá trình trình diễn trực tiếp gặp lỗi, sử dụng ảnh chụp màn hình và video ghi lại các bước triển khai, kiểm thử.

## 8. Kết quả kỳ vọng

### 8.1. Kết quả kỹ thuật

Sau khi hoàn thành đề tài, hệ thống dự kiến đạt được các kết quả sau:

- Xây dựng được website thương mại điện tử Maiora hoạt động trên Amazon EC2 và sử dụng Amazon RDS làm hệ quản trị cơ sở dữ liệu.
- Thiết lập được hệ thống sao lưu tài nguyên bằng AWS Backup và quản lý các Recovery Point thông qua Backup Vault.
- Triển khai được S3 Versioning nhằm hỗ trợ khôi phục các phiên bản dữ liệu khi xảy ra ghi đè hoặc xóa nhầm.
- Thiết lập được S3 Cross-Region Replication để duy trì bản sao hình ảnh sản phẩm tại Sydney.
- Khôi phục được các tài nguyên cần thiết từ bản sao lưu và kiểm tra khả năng hoạt động của website tại môi trường dự phòng.
- Kiểm chứng được tính toàn vẹn của dữ liệu thông qua việc đối chiếu thông tin sản phẩm, người dùng, đơn hàng và hình ảnh sau khôi phục.
- Thiết lập được hệ thống giám sát website và gửi email cảnh báo khi phát hiện sự cố.
- Xây dựng được quy trình sao lưu, khôi phục, kiểm thử và xử lý sự cố cho hệ thống BDR.

### 8.2. Tiêu chí đánh giá hiệu quả hệ thống

Đề tài đánh giá kết quả dựa trên các tiêu chí thực nghiệm sau:

- **Khả năng sao lưu:** Các tài nguyên EC2 và RDS được sao lưu thành công, có Recovery Point hợp lệ.
- **Khả năng khôi phục:** Có thể sử dụng Recovery Point để khôi phục tài nguyên và đưa hệ thống trở lại trạng thái có thể kiểm tra.
- **Tính toàn vẹn dữ liệu:** Dữ liệu sau khôi phục được đối chiếu với dữ liệu trước sự cố, bao gồm thông tin sản phẩm, tài khoản và đơn hàng.
- **Khả năng đồng bộ liên vùng:** Các đối tượng được cấu hình sao chép có thể xuất hiện tại S3 Bucket ở Sydney.
- **Khả năng duy trì hoạt động:** Website có thể được triển khai hoặc khôi phục tại môi trường dự phòng và kiểm tra các chức năng chính.
- **Hiệu quả giám sát và cảnh báo:** Hệ thống phát hiện được trạng thái website không hoạt động và gửi email thông báo đến quản trị viên.

### 8.3. Giá trị thực tiễn

Đề tài không chỉ dừng lại ở việc nghiên cứu các dịch vụ AWS riêng lẻ mà còn kết hợp chúng thành một hệ thống Backup và Disaster Recovery có thể triển khai, kiểm thử và đánh giá thực tế.

Mô hình có thể được sử dụng làm tài liệu tham khảo cho các doanh nghiệp vừa và nhỏ đang tìm kiếm giải pháp bảo vệ dữ liệu, khôi phục ứng dụng và hạn chế ảnh hưởng khi xảy ra sự cố hạ tầng đám mây.

Đồng thời, kết quả đề tài cung cấp quy trình thực hành cụ thể về AWS Backup, Amazon S3, Amazon EC2, Amazon RDS