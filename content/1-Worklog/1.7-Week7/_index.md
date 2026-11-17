
---
title: "Worklog Week 7"
date: 2026-09-21
weight: 7
chapter: false
pre: "<b>1.7.</b>"
---

### Week 7 Objectives:

- Learn about multi-Region deployment architectures on AWS.
- Analyze the data replication approach between Singapore and Sydney.
- Understand the Amazon S3 Cross-Region Replication (CRR) mechanism.
- Learn the requirements for configuring S3 Cross-Region Replication.
- Identify the roles of the primary Region and the disaster recovery Region in the Maiora Fashion Store system.
- Design an architecture diagram illustrating S3 data replication between the two Regions.

### Tasks to be implemented this week:

| Day | Tasks | Start Date | End Date | References |
|---|---|---|---|---|
| 2 | Learn about multi-Region deployment architectures on AWS and the roles of primary and disaster recovery Regions. | 21/09/2026 | 21/09/2026 | [AWS Cloud Journey](https://cloudjourney.awsstudygroup.com/) |
| 3 | Analyze the Maiora Fashion Store architecture with Singapore as the primary Region and Sydney as the disaster recovery Region. | 22/09/2026 | 22/09/2026 | [AWS Cloud Journey](https://cloudjourney.awsstudygroup.com/) |
| 4 | Learn about Amazon S3 Cross-Region Replication (CRR), Versioning, and the requirements for replicating data between two Regions. | 23/09/2026 | 24/09/2026 | [AWS Cloud Journey](https://cloudjourney.awsstudygroup.com/) |
| 5 | Learn about IAM Roles, Trust Relationships, and the permissions required for Amazon S3 Cross-Region Replication. | 25/09/2026 | 25/09/2026 | [AWS Cloud Journey](https://cloudjourney.awsstudygroup.com/) |
| 6 | Complete the S3 Cross-Region Replication architecture diagram and identify methods for verifying replicated data in the destination Region. | 26/09/2026 | 26/09/2026 | [AWS Cloud Journey](https://cloudjourney.awsstudygroup.com/) |

### Week 7 Achievements:

- Understood the multi-Region deployment architecture on AWS, in which data is distributed across different geographical locations to improve data protection and availability.

- Identified the roles of the two Regions in the Maiora Fashion Store architecture:
  - Singapore (ap-southeast-1): The primary Region hosting the Maiora Fashion Store website, Amazon EC2 application server, Amazon RDS for MySQL database, and S3 Bucket for product images.
  - Sydney (ap-southeast-2): The disaster recovery Region storing replicated product images from the Singapore S3 Bucket through Amazon S3 Cross-Region Replication.

- Learned about the Amazon S3 Cross-Region Replication (CRR) mechanism:
  - Automatically replicates eligible S3 objects from a source bucket to a destination bucket in another AWS Region.
  - Maintains copies of product images in the disaster recovery Region.
  - Requires Versioning to be enabled on both the source and destination buckets.
  - Requires a Replication Rule to define the source bucket, destination bucket, and scope of objects to be replicated.

- Learned about the components and permissions required to configure S3 Cross-Region Replication:
  - Source Bucket: The S3 Bucket in Singapore containing product images.
  - Destination Bucket: The S3 Bucket in Sydney used to store replicated objects.
  - Versioning: Manages object versions in both buckets.
  - IAM Role: Grants Amazon S3 the permissions required to perform replication.
  - Replication Rule: Defines the conditions and destination for the replication process.
  - Trust Relationship: Allows the Amazon S3 service to assume the configured IAM Role.

- Learned how to verify S3 Cross-Region Replication:
  - Check the Replication Rule status in the source bucket.
  - Verify that Versioning is enabled on both the source and destination buckets.
  - Monitor the replication status of individual S3 objects.
  - Check whether product images appear in the destination bucket in Sydney.
  - Verify that replicated objects can be accessed in the disaster recovery Region.

- Analyzed the data protection scope of the Maiora Fashion Store system:
  - Product images: Protected through S3 Cross-Region Replication from Singapore to Sydney.
  - MySQL database: Protected through Amazon RDS backup mechanisms and AWS Backup.
  - EC2 application server: Protected through AWS Backup resource backup mechanisms.

- Identified the general procedure for accessing data in the disaster recovery Region when an incident occurs:
  - Check the accessibility of the S3 Bucket in Sydney.
  - Identify the product images that have been successfully replicated.
  - Use the replicated images from the Sydney bucket when necessary.
  - Verify the integrity and accessibility of replicated objects.

- Completed the data replication architecture diagram between the two AWS Regions, illustrating the S3 Bucket in Singapore as the source and the S3 Bucket in Sydney as the destination for replicated product images through Amazon S3 Cross-Region Replication.

- Defined the actual implementation scope of the project: Amazon S3 Cross-Region Replication is used to replicate product images from Singapore (ap-southeast-1) to Sydney (ap-southeast-2). This mechanism focuses on protecting product image data and does not automatically replicate the entire website, EC2 instances, or RDS database to the disaster recovery Region.
