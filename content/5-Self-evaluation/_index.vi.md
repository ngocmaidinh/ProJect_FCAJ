---
title: "Tự đánh giá"
date: 2024-01-01
weight: 5
chapter: false
pre: " <b>5.</b> "
---

Trong suốt thời gian thực tập tại **Công ty TNHH Amazon Web Services Viet Nam** từ **10/08/2026** đến **18/10/2026**, tôi đã có cơ hội học hỏi, rèn luyện và vận dụng những kiến thức đã được trang bị tại trường vào môi trường làm việc thực tế.

Mục tiêu của tôi trong quá trình thực tập là tìm hiểu các dịch vụ điện toán đám mây của Amazon Web Services (AWS) và triển khai hệ thống Backup và Disaster Recovery trên nền tảng AWS. Trong khuôn khổ dự án, tôi đã thiết kế và triển khai mô hình hệ thống đa vùng (Multi-Region), sử dụng Singapore làm Region chính và Sydney làm Region dự phòng cho một ứng dụng web bán quần áo mẫu mang thương hiệu Maiora. Hệ thống bao gồm các thành phần chính sau:

- **Hạ tầng ứng dụng:** Triển khai máy chủ ứng dụng trên Amazon EC2 và cơ sở dữ liệu MySQL trên Amazon RDS.
- **Lưu trữ dữ liệu:** Sử dụng Amazon S3 để lưu trữ hình ảnh sản phẩm, kết hợp Versioning và Cross-Region Replication để bảo vệ và sao chép dữ liệu giữa hai Region.
- **Sao lưu dữ liệu:** Cấu hình AWS Backup Vault và Backup Plan để thực hiện sao lưu định kỳ các tài nguyên AWS được hỗ trợ, phục vụ việc khôi phục dữ liệu và tài nguyên khi xảy ra sự cố.
- **Hệ thống dự phòng đa vùng:** Triển khai môi trường dự phòng tại Region Sydney, bao gồm các tài nguyên AWS và cơ sở dữ liệu RDS độc lập, phục vụ việc khôi phục và duy trì hoạt động của ứng dụng trong các tình huống sự cố.
- **Giám sát và cảnh báo:** Tìm hiểu và cấu hình các dịch vụ Amazon CloudWatch, Amazon SNS và Route 53 phục vụ giám sát, theo dõi trạng thái và cảnh báo sự cố.
- **Bảo mật hệ thống:** Tìm hiểu và áp dụng các cơ chế bảo mật như IAM, Security Group và HTTPS.

Trong quá trình triển khai, tôi đã thực hiện các tình huống mô phỏng sự cố như mất dữ liệu, xóa nhầm đối tượng trên Amazon S3 và sự cố máy chủ ứng dụng EC2. Từ đó, tôi thực hành khôi phục dữ liệu và tài nguyên từ các bản sao lưu, kiểm tra tính toàn vẹn của dữ liệu cũng như xác minh khả năng hoạt động của website sau khi khôi phục.

Qua quá trình thực tập và thực hiện dự án, tôi đã cải thiện nhiều kỹ năng quan trọng:

- **Kiến thức chuyên môn:** Nâng cao khả năng sử dụng các dịch vụ AWS như IAM, VPC, EC2, RDS, S3, AWS Backup, CloudWatch, Route 53 và SNS; đồng thời củng cố kiến thức quản trị Linux, Apache, PHP và cơ sở dữ liệu MySQL.
- **Kỹ năng xử lý sự cố:** Rèn luyện khả năng đọc log, phân tích nguyên nhân và khắc phục các lỗi phát sinh trong quá trình triển khai, đặc biệt là các vấn đề liên quan đến phân quyền IAM, Security Group, kết nối cơ sở dữ liệu và cấu hình máy chủ web.
- **Tư duy thiết kế hệ thống:** Hiểu rõ hơn về kiến trúc hệ thống đa vùng, cơ chế sao lưu, sao chép dữ liệu liên vùng và phương án khôi phục hệ thống khi xảy ra sự cố.
- **Kỹ năng viết báo cáo và tài liệu kỹ thuật:** Biết cách ghi chép quy trình triển khai, thu thập hình ảnh minh chứng, tổng hợp kết quả và trình bày nội dung kỹ thuật một cách có hệ thống.
- **Kỹ năng tự học và làm việc:** Chủ động tìm kiếm tài liệu, nghiên cứu hướng dẫn từ AWS, thực hành kiểm tra từng cấu hình và kiên trì giải quyết các vấn đề phát sinh trong quá trình thực hiện dự án.

Nhìn chung, kỳ thực tập đã giúp tôi củng cố kiến thức chuyên môn, nâng cao kỹ năng thực hành với nền tảng AWS và có thêm kinh nghiệm trong việc triển khai, quản trị cũng như xử lý sự cố đối với một hệ thống ứng dụng trên môi trường điện toán đám mây.

Về tác phong, tôi luôn cố gắng hoàn thành tốt nhiệm vụ, tuân thủ nội quy, và tích cực trao đổi với đồng nghiệp để nâng cao hiệu quả công việc.

Để phản ánh một cách khách quan quá trình thực tập, tôi xin tự đánh giá bản thân dựa trên các tiêu chí dưới đây:


| STT | Tiêu chí                            | Mô tả                                                                                            | Tốt | Khá | Trung bình |
| --- | ----------------------------------- | ------------------------------------------------------------------------------------------------ | --- | --- | ---------- |
| 1   | **Kiến thức và kỹ năng chuyên môn** | Hiểu biết về ngành, áp dụng kiến thức vào thực tế, kỹ năng sử dụng công cụ, chất lượng công việc |☐    | ✅    | ☐       | 
| 2   | **Khả năng học hỏi**                | Tiếp thu kiến thức mới, học hỏi nhanh                                                            | ☐    | ✅    | ☐       |
| 3   | **Chủ động**                        | Tự tìm hiểu, nhận nhiệm vụ mà không chờ chỉ dẫn                                                  | ☐   | ✅   | ☐          |
| 4   | **Tinh thần trách nhiệm**           | Hoàn thành công việc đúng hạn, đảm bảo chất lượng                                                | ☐   | ✅   | ☐          |
| 5   | **Kỷ luật**                         | Tuân thủ giờ giấc, nội quy, quy trình làm việc                                                   | ✅   | ☐   | ☐          |
| 6   | **Tính cầu tiến**                   | Sẵn sàng nhận feedback và cải thiện bản thân                                                     | ✅   | ☐   | ☐          |
| 7   | **Giao tiếp**                       | Trình bày ý tưởng, báo cáo công việc rõ ràng                                                     | ☐   | ☐   | ✅          |
| 8   | **Hợp tác nhóm**                    | Làm việc hiệu quả với đồng nghiệp, tham gia nhóm                                                 | ☐   | ✅   | ☐          |
| 9   | **Ứng xử chuyên nghiệp**            | Tôn trọng đồng nghiệp, đối tác, môi trường làm việc                                              | ✅   | ☐   | ☐          |
| 10  | **Tư duy giải quyết vấn đề**        | Nhận diện vấn đề, đề xuất giải pháp, sáng tạo                                                    | ☐   | ✅   | ☐          |
| 11  | **Đóng góp vào dự án/tổ chức**      | Hiệu quả công việc, sáng kiến cải tiến, ghi nhận từ team                                         | ☐   | ☐   | ✅          |
| 12  | **Tổng thể**                        | Đánh giá chung về toàn bộ quá trình thực tập                                                     | ☐   | ✅   | ☐          |

### Cần cải thiện

* Nâng cao kỹ năng giao tiếp, trình bày ý tưởng và báo cáo công việc rõ ràng, tự tin hơn.
* Tăng cường khả năng vận dụng kiến thức chuyên môn vào thực tế và sử dụng thành thạo các công cụ chuyên ngành.
* Chủ động hơn trong việc tìm kiếm, đề xuất và triển khai các nhiệm vụ được giao.
* Cải thiện tư duy giải quyết vấn đề, mạnh dạn đề xuất các giải pháp phù hợp khi gặp khó khăn.
* Tích cực tham gia các hoạt động nhóm, nâng cao mức độ đóng góp vào dự án và đề xuất sáng kiến cải tiến công việc.
* Tiếp tục phát huy tinh thần học hỏi, trách nhiệm và cầu tiến để nâng cao chất lượng công việc.