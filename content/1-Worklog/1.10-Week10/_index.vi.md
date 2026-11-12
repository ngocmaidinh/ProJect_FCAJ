---
title: "Nhật ký thực tập Tuần 10"
date: 2026-10-12
weight: 10
chapter: false
pre: "<b>1.10.</b>"
---

### Mục tiêu tuần 10:

- Rà soát và hoàn thiện cấu hình hệ thống Backup và Disaster Recovery.
- Tổng hợp kiến trúc hệ thống, quy trình triển khai và kết quả kiểm thử.
- Rà soát hiệu quả của các cơ chế sao lưu, khôi phục và bảo vệ dữ liệu liên vùng.
- Hoàn thiện báo cáo thực tập và tài liệu kỹ thuật phục vụ khóa luận tốt nghiệp.
- Hoàn thiện tài liệu FCAJ Workshop bằng tiếng Anh và tiếng Việt.
- Tổng kết quá trình triển khai dự án cùng những kiến thức và kỹ năng tích lũy được trong thời gian thực tập.

### Công việc cần thực hiện trong tuần:

| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành |
|---|---|---|---|
| Thứ Hai | Rà soát kiến trúc, cấu hình và trạng thái các tài nguyên AWS trong hệ thống. | 12/10/2026 | 12/10/2026 |
| Thứ Ba | Tổng hợp sơ đồ kiến trúc, ảnh minh chứng và kết quả triển khai, kiểm thử. | 13/10/2026 | 13/10/2026 |
| Thứ Tư | Rà soát kết quả sao lưu và khôi phục, kiểm tra các kịch bản sự cố đã mô phỏng và xác định hạn chế của hệ thống. | 14/10/2026 | 15/10/2026 |
| Thứ Sáu | Viết, chỉnh sửa và rà soát báo cáo thực tập cùng tài liệu kỹ thuật. | 16/10/2026 | 16/10/2026 |
| Chủ Nhật | Kiểm tra lần cuối, hoàn thiện tài liệu Workshop song ngữ và tổng kết quá trình thực tập. | 18/10/2026 | 18/10/2026 |

### Kết quả đạt được trong tuần 10:

- Rà soát và tổng hợp kiến trúc hệ thống Backup và Disaster Recovery cho website Maiora Fashion Store với các dịch vụ AWS chính:
  - Amazon VPC: Cung cấp môi trường mạng và phân chia các public subnet, private subnet.
  - Amazon EC2: Vận hành máy chủ ứng dụng website.
  - Amazon EBS: Cung cấp ổ đĩa lưu trữ cho EC2 Instance.
  - Amazon RDS for MySQL: Lưu trữ cơ sở dữ liệu của website.
  - Amazon S3: Lưu trữ hình ảnh sản phẩm, sử dụng Versioning và Cross-Region Replication.
  - AWS Backup: Quản lý hoạt động sao lưu và lưu trữ Recovery Point cho EC2 và RDS.

- Rà soát vai trò của các dịch vụ bảo mật và quản lý quyền truy cập:
  - AWS IAM: Quản lý người dùng, vai trò và quyền truy cập tài nguyên.
  - Security Groups: Kiểm soát lưu lượng mạng vào và ra đối với EC2 và RDS.
  - S3 Bucket Policies: Quản lý quyền truy cập đối với các đối tượng trong S3 Bucket.
  - IAM Roles: Cung cấp quyền cần thiết để các dịch vụ AWS thực hiện thao tác sao lưu và khôi phục.

- Tìm hiểu các dịch vụ AWS bổ trợ liên quan đến giám sát và khôi phục sau thảm họa:
  - Amazon CloudWatch: Giám sát các chỉ số và trạng thái tài nguyên AWS.
  - Amazon SNS: Hỗ trợ gửi thông báo về các sự kiện và cảnh báo.
  - Amazon Route 53: Quản lý DNS và hỗ trợ định tuyến lưu lượng.
  - AWS Elastic Disaster Recovery: Cung cấp khả năng khôi phục máy chủ trong các tình huống thảm họa.

- Hoàn thiện và rà soát các sơ đồ kiến trúc hệ thống:
  - Sơ đồ kiến trúc mạng VPC và các thành phần triển khai website.
  - Luồng kết nối giữa EC2 và RDS.
  - Luồng truy cập hình ảnh sản phẩm từ Amazon S3.
  - Quy trình tạo bản sao lưu và Recovery Point bằng AWS Backup.
  - Quy trình khôi phục máy chủ ứng dụng EC2 và cơ sở dữ liệu RDS.
  - Quy trình sao chép hình ảnh sản phẩm từ Singapore (`ap-southeast-1`) sang Sydney (`ap-southeast-2`) thông qua S3 Cross-Region Replication.

- Tổng hợp hình ảnh minh chứng triển khai và kết quả kiểm thử:
  - Cấu hình VPC, subnet, route table và Security Group.
  - Trạng thái EC2 Instance và cơ sở dữ liệu RDS.
  - Cấu hình và trạng thái AWS Backup.
  - Backup Job và Recovery Point.
  - Kết quả khôi phục EC2 và RDS.
  - Cấu hình S3 Versioning và Cross-Region Replication.
  - Kết quả kiểm tra chức năng website sau khi khôi phục.

- Rà soát kết quả sao lưu và khôi phục:
  - Kiểm tra các Recovery Point hiện có của tài nguyên EC2 và RDS.
  - Rà soát quy trình khôi phục và các cấu hình cần thiết sau khi phục hồi.
  - Kiểm tra khả năng hoạt động của máy chủ ứng dụng sau khi khôi phục.
  - Kiểm tra kết nối cơ sở dữ liệu và chức năng website sau khi phục hồi.
  - Rà soát khả năng khôi phục hình ảnh sản phẩm bằng S3 Versioning.
  - Tìm hiểu vai trò của Cross-Region Replication trong việc bảo vệ dữ liệu hình ảnh sản phẩm giữa các AWS Region.

- Đánh giá ưu điểm của hệ thống:
  - Quản lý sao lưu tập trung cho EC2 và RDS thông qua AWS Backup.
  - Recovery Point cung cấp cơ sở để khôi phục tài nguyên khi xảy ra sự cố.
  - S3 Versioning hỗ trợ khôi phục các phiên bản đối tượng trước đó.
  - S3 Cross-Region Replication hỗ trợ bảo vệ dữ liệu hình ảnh sản phẩm tại một Region khác.
  - Việc tách biệt máy chủ ứng dụng và cơ sở dữ liệu giúp nâng cao khả năng quản lý tài nguyên và kiểm soát truy cập.

- Rà soát hạn chế và chi phí vận hành của hệ thống:
  - Quá trình khôi phục EC2 và RDS vẫn cần thực hiện thêm một số bước cấu hình.
  - Chưa triển khai cơ chế tự động chuyển đổi toàn bộ website sang Region Sydney khi xảy ra sự cố.
  - Quá trình khôi phục có thể phát sinh thêm các bước cấu hình và chi phí tài nguyên.
  - Cần quản lý thời gian lưu trữ Recovery Point, dung lượng lưu trữ và chi phí truyền dữ liệu.
  - Cần thực hiện kiểm thử khôi phục định kỳ để đảm bảo các bản sao lưu có thể sử dụng khi cần thiết.

- Hoàn thiện báo cáo thực tập và tài liệu kỹ thuật:
  - Rà soát nội dung các chương trong báo cáo.
  - Bổ sung sơ đồ kiến trúc, hình ảnh cấu hình và kết quả kiểm thử.
  - Thống nhất cách trình bày bảng biểu, thuật ngữ AWS và định dạng tài liệu.
  - Tổng hợp tài liệu tham khảo.
  - Hoàn thiện tài liệu phục vụ khóa luận tốt nghiệp với đề tài "Nghiên cứu và xây dựng hệ thống Backup và Disaster Recovery trên Amazon Web Services (AWS)".

- Hoàn thiện tài liệu FCAJ Workshop:
  - Sắp xếp nội dung Workshop thành các phần có cấu trúc rõ ràng.
  - Xây dựng hướng dẫn triển khai và quy trình cấu hình các dịch vụ AWS.
  - Bổ sung hình ảnh minh họa quá trình triển khai và cấu hình.
  - Rà soát và hoàn thiện tài liệu tiếng Anh và tiếng Việt.
  - Kiểm tra cấu trúc điều hướng và cách hiển thị nội dung Workshop.

- Tổng kết quá trình thực tập:
  - Củng cố kiến thức về điện toán đám mây và các dịch vụ AWS.
  - Nâng cao kỹ năng cấu hình, triển khai và quản lý tài nguyên AWS.
  - Hiểu rõ hơn về quy trình sao lưu, khôi phục và kiểm thử Disaster Recovery.
  - Cải thiện kỹ năng xử lý sự cố, đọc hiểu trạng thái tài nguyên và xây dựng tài liệu kỹ thuật.