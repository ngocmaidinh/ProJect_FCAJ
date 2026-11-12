
---
title: "Week 8 Worklog"
date: 2026-09-28
weight: 8
chapter: false
pre: "<b>1.8.</b>"
---

### Week 8 Objectives:

- Practice restoring AWS resources from backups.
- Verify data integrity after restoration.
- Evaluate the recoverability of the Maiora Fashion Store website.
- Identify additional configurations required to bring the system back to an operational state.

### Tasks to Be Completed This Week:

| Day | Tasks | Start Date | Completion Date | Reference Materials |
|---|---|---|---|---|
| Monday | Inspect EC2 and RDS Recovery Points and select suitable backups for restoration testing. | 28/09/2026 | 28/09/2026 | [AWS Backup Documentation](https://docs.aws.amazon.com/aws-backup/) |
| Tuesday | Restore the EC2 application server from an AWS Backup Recovery Point and verify its configuration. | 29/09/2026 | 29/09/2026 | [AWS Backup Documentation](https://docs.aws.amazon.com/aws-backup/) |
| Wednesday | Restore the RDS database from a suitable Recovery Point or snapshot. | 30/09/2026 | 01/10/2026 | [Amazon RDS Documentation](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/) |
| Friday | Inspect Amazon S3 Versioning and study how to restore product image object versions. | 02/10/2026 | 02/10/2026 | [Amazon S3 Versioning](https://docs.aws.amazon.com/AmazonS3/latest/userguide/Versioning.html) |
| Saturday | Verify website functionality, database availability, and product images after restoration. | 03/10/2026 | 03/10/2026 | [AWS Backup Documentation](https://docs.aws.amazon.com/aws-backup/) |

### Week 8 Achievements:

- Understood the AWS resource restoration process using Recovery Points and snapshots, including backup selection, restoration initiation, and post-restoration verification.

- Practiced and studied application server recovery:
  - Amazon EC2.
  - Amazon EBS.
  - AWS Backup Recovery Points.
  - Verified the EC2 instance status after restoration.
  - Inspected Security Groups, subnets, IP addresses, and related network configurations.
  - Identified additional configurations required for the application server to resume website services.

- Practiced database restoration:
  - Amazon RDS for MySQL.
  - AWS Backup Recovery Points and RDS snapshots.
  - Verified the database status after restoration.
  - Identified the endpoint of the restored RDS instance.
  - Inspected the connection configuration between the PHP application and the database.
  - Identified the application configuration changes required when the database endpoint changes.

- Studied and inspected the image data recovery mechanism:
  - Amazon S3 Versioning.
  - Object versions stored in the S3 bucket.
  - Restoring an appropriate object version when data is overwritten or deleted.
  - Verifying image paths and accessibility after restoration.
  - Understanding the difference between a Delete Marker and permanently deleting an object version.

- Verified Maiora Fashion Store website functionality after restoration:
  - Accessed the website homepage.
  - Checked product listings and product information.
  - Tested relevant application functions.
  - Verified database connectivity.
  - Checked product image loading from Amazon S3.

- Used the AWS Management Console and resource status information to identify issues encountered during restoration.

- Recorded configurations that may need to be checked or updated after restoration:
  - RDS endpoint and connection settings.
  - Security Groups and network configuration.
  - Elastic IP reassociation, when required.
  - PHP application configuration.
  - S3 image paths and access permissions.

- Understood that restoring resources from Recovery Points does not guarantee that the entire website will automatically resume operation. Compatibility between the application server, database, network configuration, and image data must be verified.

- Evaluated system recoverability by checking resource statuses and website functionality after restoration.
