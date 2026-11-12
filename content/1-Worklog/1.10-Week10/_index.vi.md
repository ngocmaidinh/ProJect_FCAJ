
---
title: "Worklog Tuần 10"
date: 2026-10-12
weight: 10
chapter: false
pre: "<b>1.10.</b>"
---

### Mục tiêu tuần 10:

- Rà soát và hoàn thiện các cấu hình của hệ thống Backup và Disaster Recovery.
- Tổng hợp kiến trúc, quy trình triển khai và kết quả kiểm thử.
- Đánh giá hiệu quả của phương án sao lưu và khôi phục thông qua các chỉ số RTO và RPO.
- Hoàn thiện báo cáo thực tập và tài liệu kỹ thuật phục vụ khóa luận tốt nghiệp.
- Tổng kết quá trình thực hiện đề tài và những kiến thức, kỹ năng đạt được.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành |
|---|---|---|---|
| 2 | Rà soát kiến trúc, cấu hình và trạng thái các tài nguyên AWS trong hệ thống. | 12/10/2026 | 12/10/2026 |
| 3 | Tổng hợp sơ đồ kiến trúc, ảnh minh chứng và kết quả triển khai, kiểm thử. | 13/10/2026 | 13/10/2026 |
| 4 | Hoàn thiện bảng kết quả RTO, RPO và đánh giá các kịch bản mô phỏng sự cố. | 14/10/2026 | 15/10/2026 |
| 5 | Viết, chỉnh sửa và rà soát báo cáo thực tập, trình bày các kết quả đạt được. | 16/10/2026 | 16/10/2026 |
| 7 | Kiểm tra lần cuối, hoàn thiện báo cáo và tổng kết quá trình thực tập. | 18/10/2026 | 18/10/2026 |

### Kết quả đạt được tuần 10:

- Rà soát và tổng hợp kiến trúc hệ thống Backup và Disaster Recovery cho website Maiora Fashion Store, sử dụng các dịch vụ AWS chính:
  - Amazon VPC: Xây dựng môi trường mạng và phân chia Public Subnet, Private Subnet.
  - Amazon EC2: Triển khai máy chủ ứng dụng website.
  - Amazon EBS: Lưu trữ dữ liệu và ổ đĩa của máy chủ EC2.
  - Amazon RDS for MySQL: Lưu trữ cơ sở dữ liệu của website.
  - Amazon S3: Lưu trữ hình ảnh sản phẩm, sử dụng Versioning và Cross-Region Replication.
  - AWS Backup: Quản lý hoạt động sao lưu và lưu trữ Recovery Point cho EC2 và RDS.

- Tổng hợp vai trò của các dịch vụ bảo mật và quản lý truy cập:
  - AWS IAM: Quản lý người dùng, vai trò và quyền truy cập tài nguyên.
  - Security Group: Kiểm soát lưu lượng mạng đến và đi của EC2 và RDS.
  - S3 Bucket Policy: Quản lý quyền truy cập đối tượng trong bucket S3.
  - IAM Role: Cung cấp quyền cần thiết cho các dịch vụ AWS thực hiện hoạt động sao lưu và khôi phục.

- Tổng hợp các dịch vụ hỗ trợ đã tìm hiểu:
  - Amazon CloudWatch: Theo dõi chỉ số và trạng thái tài nguyên AWS.
  - Amazon SNS: Hỗ trợ gửi thông báo khi có sự kiện hoặc cảnh báo.
  - Amazon Route 53: Quản lý DNS và hỗ trợ định tuyến lưu lượng.
  - AWS Elastic Disaster Recovery: Hỗ trợ xây dựng phương án phục hồi máy chủ khi xảy ra sự cố.

- Hoàn thiện và rà soát sơ đồ kiến trúc hệ thống:
  - Kiến trúc mạng VPC và các thành phần triển khai website.
  - Luồng kết nối giữa EC2 và RDS.
  - Luồng truy cập hình ảnh sản phẩm từ Amazon S3.
  - Quy trình sao lưu và tạo Recovery Point bằng AWS Backup.
  - Quy trình khôi phục máy chủ EC2 và cơ sở dữ liệu RDS.
  - Cơ chế sao chép dữ liệu hình ảnh từ Singapore (`ap-southeast-1`) sang Sydney (`ap-southeast-2`) bằng S3 Cross-Region Replication.

- Tổng hợp ảnh minh chứng và kết quả triển khai, kiểm thử:
  - Cấu hình VPC, Subnet, Route Table và Security Group.
  - Trạng thái máy chủ EC2 và cơ sở dữ liệu RDS.
  - Cấu hình và trạng thái AWS Backup.
  - Backup Job và Recovery Point.
  - Kết quả khôi phục EC2 và RDS.
  - Cấu hình Versioning và Cross-Region Replication của S3.
  - Kết quả kiểm tra hoạt động website sau khôi phục.

- Hoàn thiện bảng đánh giá RTO và RPO:
  - Tổng hợp thời điểm bắt đầu sự cố hoặc quá trình khôi phục theo kịch bản kiểm thử.
  - Ghi nhận thời điểm tài nguyên được khôi phục.
  - Xác định thời điểm website hoạt động trở lại.
  - Tính toán thời gian phục hồi thực tế.
  - Đánh giá khoảng thời gian dữ liệu có thể bị mất dựa trên Recovery Point được sử dụng.
  - So sánh kết quả kiểm thử với mục tiêu RTO/RPO dự kiến.

- Đánh giá ưu điểm của hệ thống:
  - Tập trung hóa hoạt động sao lưu tài nguyên EC2 và RDS bằng AWS Backup.
  - Sử dụng Recovery Point làm cơ sở khôi phục khi xảy ra sự cố.
  - S3 Versioning hỗ trợ phục hồi các phiên bản đối tượng phù hợp.
  - S3 Cross-Region Replication hỗ trợ bảo vệ dữ liệu hình ảnh tại Region khác.
  - Phân tách máy chủ ứng dụng và cơ sở dữ liệu giúp quản lý tài nguyên và kiểm soát truy cập tốt hơn.

- Đánh giá hạn chế và chi phí:
  - Quá trình khôi phục EC2 và RDS vẫn cần thực hiện các bước cấu hình bổ sung.
  - Chưa triển khai cơ chế tự động chuyển đổi toàn bộ website sang Sydney.
  - Việc khôi phục có thể phát sinh thời gian chờ và chi phí sử dụng tài nguyên.
  - Cần quản lý thời gian lưu giữ Recovery Point, dung lượng lưu trữ và chi phí truyền dữ liệu.
  - Cần kiểm thử định kỳ để đảm bảo các bản sao lưu có thể sử dụng khi cần thiết.

- Hoàn thiện báo cáo thực tập và tài liệu kỹ thuật:
  - Rà soát nội dung các chương trong báo cáo.
  - Bổ sung sơ đồ kiến trúc, hình ảnh cấu hình và kết quả kiểm thử.
  - Chuẩn hóa bảng biểu, thuật ngữ AWS và cách trình bày.
  - Tổng hợp các tài liệu tham khảo.
  - Hoàn thiện nội dung phục vụ khóa luận tốt nghiệp với đề tài “Thiết kế và triển khai hệ thống Backup và Disaster Recovery trên Amazon Web Services (AWS)”.

- Tổng kết quá trình thực tập:
  - Củng cố kiến thức về điện toán đám mây và các dịch vụ AWS.
  - Nâng cao kỹ năng cấu hình, triển khai và quản lý tài nguyên trên AWS.
  - Hiểu rõ quy trình sao lưu, khôi phục và kiểm thử Disaster Recovery.
  - Rèn luyện kỹ năng phân tích sự cố, đọc trạng thái tài nguyên và xây dựng tài liệu kỹ thuật.
