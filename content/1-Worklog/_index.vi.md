---
title: "Nhật ký thực tập"
date: 2026-08-10
weight: 1
chapter: false
pre: "<b>1.</b>"
---

# Nhật ký thực tập

### Tổng quan

Phần này trình bày nhật ký thực tập của tôi trong thời gian 10 tuần, từ ngày 10/08/2026 đến ngày 18/10/2026.

Trong thời gian thực tập, tôi đã nghiên cứu, thiết kế và triển khai hệ thống Sao lưu và Khôi phục sau thảm họa (Backup and Disaster Recovery – DR) trên nền tảng Amazon Web Services (AWS), sử dụng website thương mại điện tử thời trang Maiora làm ứng dụng thực tế để triển khai và kiểm thử.

Song song với quá trình triển khai kỹ thuật, tôi đã xây dựng tài liệu FCAJ Workshop nhằm trình bày kiến trúc hệ thống, cấu hình các dịch vụ AWS, quy trình triển khai ứng dụng, chiến lược sao lưu và các phương án khôi phục sau sự cố. Nội dung Workshop bao quát toàn bộ quá trình thực hiện, từ chuẩn bị môi trường, thiết kế kiến trúc đến cấu hình sao lưu, khôi phục tài nguyên và kiểm thử khả năng phục hồi của hệ thống.

Các hoạt động thực tập tập trung vào việc xây dựng hạ tầng điện toán đám mây, triển khai website Maiora, cấu hình cơ sở dữ liệu và lưu trữ, thiết lập cơ chế sao lưu và bảo vệ dữ liệu liên vùng, thực hiện các thử nghiệm khôi phục và hoàn thiện tài liệu Workshop song ngữ.

Các công việc chính được thực hiện trong thời gian thực tập được tổng hợp như sau:

### Nội dung công việc theo tuần

**Tuần 1:** [Giới thiệu dự án và chuẩn bị môi trường AWS](1.1-week1/)

Tìm hiểu chương trình thực tập, mục tiêu dự án và các quy định làm việc. Làm quen với AWS Management Console, AWS CLI và các dịch vụ cơ bản của AWS để chuẩn bị cho quá trình triển khai dự án.

**Tuần 2:** [Phân tích yêu cầu và thiết kế kiến trúc hệ thống](1.2-week2/)

Xác định các yêu cầu của hệ thống, tìm hiểu các khái niệm về Backup và Disaster Recovery, lựa chọn các dịch vụ AWS phù hợp và thiết kế kiến trúc môi trường chính và môi trường khôi phục dự phòng tại hai Region Singapore và Sydney.

**Tuần 3:** [Triển khai Amazon VPC và hạ tầng mạng](1.3-week3/)

Tạo Amazon VPC, cấu hình dải địa chỉ CIDR, các public subnet và private subnet, route table, Internet Gateway và Security Group nhằm xây dựng hạ tầng mạng cho hệ thống.

**Tuần 4:** [Triển khai Amazon EC2 và website Maiora](1.4-week4/)

Khởi tạo EC2 làm máy chủ ứng dụng, chuẩn bị môi trường Amazon Linux, cài đặt và cấu hình Apache, PHP, sau đó triển khai website thương mại điện tử thời trang Maiora.

**Tuần 5:** [Cấu hình Amazon RDS và Amazon S3](1.5-week5/)

Khởi tạo và cấu hình cơ sở dữ liệu MySQL trên Amazon RDS, kết nối máy chủ ứng dụng với cơ sở dữ liệu, cấu hình Amazon S3 để lưu trữ hình ảnh sản phẩm và kích hoạt tính năng S3 Versioning.

**Tuần 6:** [Cấu hình AWS Backup và bảo vệ dữ liệu liên vùng](1.6-week6/)

Tạo AWS Backup Vault và Backup Plan, cấu hình sao lưu cho các tài nguyên EC2 và RDS, tìm hiểu Backup Job và Recovery Point, đồng thời thiết lập S3 Cross-Region Replication giữa hai Region Singapore và Sydney.

**Tuần 7:** [Chuẩn bị môi trường khôi phục sau thảm họa](1.7-week7/)

Chuẩn bị môi trường khôi phục dự phòng tại Region Sydney, tìm hiểu phương án khôi phục tài nguyên giữa các Region và rà soát quy trình phục hồi hệ thống từ các bản sao lưu đã tạo.

**Tuần 8:** [Khôi phục bản sao lưu và kiểm tra tính toàn vẹn dữ liệu](1.8-week8/)

Thực hiện khôi phục tài nguyên từ các Recovery Point của AWS Backup, kiểm tra khả năng hoạt động của ứng dụng sau khi khôi phục và xác minh tính toàn vẹn, nhất quán của dữ liệu được phục hồi.

**Tuần 9:** [Xây dựng kịch bản và kiểm thử khôi phục sau thảm họa](1.9-week9/)

Thực hiện các kịch bản khôi phục ứng dụng và dữ liệu, mô phỏng một số tình huống sự cố có thể xảy ra, tìm hiểu quy trình phục hồi và kiểm tra khả năng hoạt động của ứng dụng cũng như cơ sở dữ liệu sau khi khôi phục.

**Tuần 10:** [Hoàn thiện tài liệu Workshop và tổng kết dự án](1.10-week10/)

Rà soát kiến trúc AWS và các quy trình triển khai, tổng hợp hình ảnh minh chứng và kết quả thực hiện, hoàn thiện tài liệu FCAJ Workshop song ngữ, tổng kết quá trình triển khai và kiểm thử khôi phục, đồng thời hoàn thiện báo cáo thực tập.