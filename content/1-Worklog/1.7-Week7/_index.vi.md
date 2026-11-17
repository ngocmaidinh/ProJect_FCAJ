
---
title: "Worklog Tuần 7"
date: 2026-09-21
weight: 7
chapter: false
pre: "<b>1.7.</b>"
---

### Mục tiêu tuần 7:

- Tìm hiểu mô hình triển khai hệ thống trên nhiều AWS Region.
- Phân tích phương án sao chép dữ liệu giữa Singapore và Sydney.
- Tìm hiểu cơ chế Amazon S3 Cross-Region Replication (CRR).
- Tìm hiểu các yêu cầu cần thiết để cấu hình S3 Cross-Region Replication.
- Xác định vai trò của Region chính và Region dự phòng trong hệ thống Maiora Fashion Store.
- Xây dựng sơ đồ kiến trúc sao chép dữ liệu S3 giữa hai Region.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
|---|---|---|---|---|
| 2 | Tìm hiểu kiến trúc triển khai hệ thống trên nhiều AWS Region và vai trò của Region chính, Region dự phòng. | 21/09/2026 | 21/09/2026 | [AWS Cloud Journey](https://cloudjourney.awsstudygroup.com/) |
| 3 | Phân tích kiến trúc hệ thống Maiora Fashion Store với Singapore là Region chính và Sydney là Region dự phòng. | 22/09/2026 | 22/09/2026 | [AWS Cloud Journey](https://cloudjourney.awsstudygroup.com/) |
| 4 | Tìm hiểu Amazon S3 Cross-Region Replication (CRR), Versioning và các yêu cầu cấu hình sao chép dữ liệu giữa hai Region. | 23/09/2026 | 24/09/2026 | [AWS Cloud Journey](https://cloudjourney.awsstudygroup.com/) |
| 5 | Tìm hiểu IAM Role, Trust Relationship và quyền truy cập cần thiết để Amazon S3 thực hiện Cross-Region Replication. | 25/09/2026 | 25/09/2026 | [AWS Cloud Journey](https://cloudjourney.awsstudygroup.com/) |
| 6 | Hoàn thiện sơ đồ kiến trúc S3 Cross-Region Replication và xác định phương pháp kiểm tra dữ liệu được sao chép sang Region đích. | 26/09/2026 | 26/09/2026 | [AWS Cloud Journey](https://cloudjourney.awsstudygroup.com/) |

### Kết quả đạt được tuần 7:

- Hiểu được mô hình triển khai hệ thống trên nhiều AWS Region, trong đó dữ liệu được phân bố giữa các khu vực địa lý khác nhau nhằm tăng khả năng bảo vệ và sẵn sàng truy cập dữ liệu.

- Tìm hiểu và xác định vai trò của hai Region trong kiến trúc Maiora Fashion Store:
  - Singapore (ap-southeast-1): Region chính, triển khai website Maiora Fashion Store, máy chủ ứng dụng Amazon EC2, cơ sở dữ liệu Amazon RDS for MySQL và S3 Bucket lưu trữ hình ảnh sản phẩm.
  - Sydney (ap-southeast-2): Region dự phòng, lưu trữ bản sao hình ảnh sản phẩm được sao chép từ S3 tại Singapore thông qua Amazon S3 Cross-Region Replication.

- Tìm hiểu cơ chế Amazon S3 Cross-Region Replication (CRR):
  - Tự động sao chép các đối tượng S3 đáp ứng điều kiện của Replication Rule từ bucket nguồn sang bucket đích tại AWS Region khác.
  - Hỗ trợ duy trì bản sao dữ liệu hình ảnh sản phẩm tại Region dự phòng.
  - Yêu cầu bật Versioning trên cả bucket nguồn và bucket đích.
  - Cần cấu hình Replication Rule để xác định bucket nguồn, bucket đích và phạm vi đối tượng được sao chép.

- Tìm hiểu các thành phần và quyền cần thiết khi cấu hình S3 Cross-Region Replication:
  - Source Bucket: S3 Bucket tại Singapore chứa hình ảnh sản phẩm.
  - Destination Bucket: S3 Bucket tại Sydney dùng để lưu trữ bản sao.
  - Versioning: Quản lý các phiên bản đối tượng trên cả hai bucket.
  - IAM Role: Cung cấp quyền cho Amazon S3 thực hiện quá trình sao chép dữ liệu.
  - Replication Rule: Xác định điều kiện và đích đến của quá trình sao chép.
  - Trust Relationship: Cho phép dịch vụ Amazon S3 sử dụng IAM Role được cấu hình.

- Tìm hiểu cách kiểm tra hoạt động của S3 Cross-Region Replication:
  - Kiểm tra trạng thái Replication Rule tại bucket nguồn.
  - Kiểm tra Versioning trên cả bucket nguồn và bucket đích.
  - Theo dõi trạng thái replication của từng đối tượng S3.
  - Kiểm tra sự xuất hiện của hình ảnh sản phẩm tại bucket đích ở Sydney.
  - Xác minh dữ liệu được sao chép có thể truy cập tại Region dự phòng.

- Phân tích phạm vi bảo vệ dữ liệu của hệ thống Maiora Fashion Store:
  - Hình ảnh sản phẩm: Sử dụng S3 Cross-Region Replication để sao chép từ Singapore sang Sydney.
  - Cơ sở dữ liệu MySQL: Được bảo vệ thông qua cơ chế sao lưu của Amazon RDS và AWS Backup.
  - Máy chủ ứng dụng EC2: Được bảo vệ thông qua cơ chế sao lưu tài nguyên bằng AWS Backup.

- Xác định quy trình sử dụng dữ liệu tại Region dự phòng khi xảy ra sự cố:
  - Kiểm tra khả năng truy cập S3 Bucket tại Sydney.
  - Xác định các hình ảnh sản phẩm đã được sao chép.
  - Sử dụng dữ liệu hình ảnh từ bucket tại Sydney khi cần thiết.
  - Kiểm tra tính toàn vẹn và khả năng truy cập của các đối tượng được sao chép.

- Hoàn thiện sơ đồ kiến trúc sao chép dữ liệu giữa hai AWS Region, thể hiện S3 Bucket tại Singapore là nguồn dữ liệu và S3 Bucket tại Sydney là nơi lưu trữ các bản sao hình ảnh sản phẩm thông qua Amazon S3 Cross-Region Replication.

- Xác định phạm vi triển khai thực tế của đề tài: sử dụng Amazon S3 Cross-Region Replication để sao chép hình ảnh sản phẩm từ Singapore (ap-southeast-1) sang Sydney (ap-southeast-2). Cơ chế này tập trung bảo vệ dữ liệu hình ảnh sản phẩm, không thực hiện sao chép tự động toàn bộ website, EC2 hoặc cơ sở dữ liệu RDS sang Region dự phòng.
