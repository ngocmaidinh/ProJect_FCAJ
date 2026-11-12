
---
title: "Week 5 Worklog"
date: 2026-09-07
weight: 5
chapter: false
pre: "<b>1.5.</b>"
---

### Week 5 Objectives:

- Study Amazon S3 and object storage mechanisms on AWS.
- Deploy an S3 Bucket to store product images for the Maiora Fashion Store website.
- Integrate Amazon S3 with the PHP website to separate image storage from the application server.
- Configure S3 Versioning to protect and manage object versions.
- Study and implement Cross-Region Replication to replicate data from the Singapore Region to the Sydney Region.

### Tasks to Be Completed This Week:

| Day | Tasks | Start Date | Completion Date | Reference Materials |
|---|---|---|---|---|
| Monday | Study Amazon S3, Buckets, Objects, Object Keys, and storage classes. | 07/09/2026 | 07/09/2026 | [Amazon S3 Documentation](https://docs.aws.amazon.com/s3/) |
| Tuesday | Create an S3 Bucket in the Singapore Region and upload product images to the `products/` folder. | 08/09/2026 | 08/09/2026 | [Amazon S3 Documentation](https://docs.aws.amazon.com/s3/) |
| Wednesday | Configure access permissions and integrate S3 image URLs into the Maiora Fashion Store website. | 09/09/2026 | 10/09/2026 | [Amazon S3 Documentation](https://docs.aws.amazon.com/s3/) |
| Friday | Enable S3 Versioning and study object version management and data protection policies. | 11/09/2026 | 11/09/2026 | [Managing S3 Versioning](https://docs.aws.amazon.com/AmazonS3/latest/userguide/Versioning.html) |
| Saturday | Create a bucket in the Sydney Region and configure Cross-Region Replication from Singapore to Sydney. | 12/09/2026 | 12/09/2026 | [S3 Replication Documentation](https://docs.aws.amazon.com/AmazonS3/latest/userguide/replication.html) |

### Week 5 Achievements:

- Understood Amazon S3 and its role in storing, managing, and protecting object data on AWS.

- Gained knowledge of the fundamental Amazon S3 components:
  - Bucket.
  - Object.
  - Object Key.
  - Bucket Policy.
  - Storage Class.

- Implemented product image storage on Amazon S3:
  - Created an S3 Bucket in the Singapore Region.
  - Uploaded product images to the bucket.
  - Organized images in the `products/` folder.
  - Inspected and managed stored objects.

- Integrated Amazon S3 with the Maiora Fashion Store website:
  - Configured image storage paths.
  - Updated the PHP application to retrieve product images from S3 instead of storing them directly on the EC2 instance.
  - Verified product image display on the website.

- Studied and configured S3 data protection mechanisms:
  - S3 Versioning.
  - S3 Cross-Region Replication.
  - IAM Policy.
  - S3 Bucket Policy.
  - Block Public Access and access control settings.

- Understood how S3 Versioning retains multiple versions of an object and supports retrieving previous versions when data is accidentally overwritten or deleted.

- Studied and implemented S3 Cross-Region Replication:
  - Used the Singapore Region (`ap-southeast-1`) as the source Region.
  - Used the Sydney Region (`ap-southeast-2`) as the destination Region.
  - Configured the destination bucket and IAM permissions required for replication.
  - Created replication rules for eligible objects.
  - Verified the presence of replicated data in the destination bucket.

- Understood the differences between S3 Versioning and Cross-Region Replication and the role of each mechanism in a data protection strategy.

- Completed product image storage on S3 and established a data protection mechanism across two AWS Regions, providing the foundation for recovery testing in subsequent weeks.
