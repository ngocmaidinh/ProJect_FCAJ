
---
title: "Week 6 Worklog"
date: 2026-09-14
weight: 6
chapter: false
pre: "<b>1.6.</b>"
---

### Week 6 Objectives:

- Study AWS Backup and centralized backup management on AWS.
- Create a Backup Vault to store recovery points.
- Configure Backup Plans and Backup Rules for protected resources.
- Perform backups of Amazon EC2 and Amazon RDS.
- Verify Backup Job statuses and Recovery Points.
- Study IAM Roles and the permissions required for backup and resource restoration.

### Tasks to Be Completed This Week:

| Day | Tasks | Start Date | Completion Date | Reference Materials |
|---|---|---|---|---|
| Monday | Study AWS Backup, Backup Vaults, Backup Plans, Backup Jobs, and Recovery Points. | 14/09/2026 | 14/09/2026 | [AWS Backup Documentation](https://docs.aws.amazon.com/aws-backup/) |
| Tuesday | Create the `BackupDR-Vault` Backup Vault and study Backup Plan and Backup Rule configuration. | 15/09/2026 | 15/09/2026 | [AWS Backup Documentation](https://docs.aws.amazon.com/aws-backup/) |
| Wednesday | Select and configure Amazon EC2 and Amazon RDS resources for protection using AWS Backup. | 16/09/2026 | 17/09/2026 | [AWS Backup Documentation](https://docs.aws.amazon.com/aws-backup/) |
| Friday | Perform test backups and monitor Backup Job statuses for EC2 and RDS. | 18/09/2026 | 18/09/2026 | [AWS Backup Documentation](https://docs.aws.amazon.com/aws-backup/) |
| Saturday | Inspect Recovery Points, backup creation times, retention periods, and factors affecting backup costs. | 19/09/2026 | 19/09/2026 | [AWS Backup Documentation](https://docs.aws.amazon.com/aws-backup/) |

### Week 6 Achievements:

- Understood AWS Backup and its role in managing, automating, and centralizing backup operations for AWS resources.

- Gained knowledge of the main AWS Backup components:
  - Backup Plan.
  - Backup Rule.
  - Backup Vault.
  - Recovery Point.
  - Backup Job.
  - Restore Job.

- Configured the backup environment:
  - Created a Backup Vault named `BackupDR-Vault`.
  - Studied and configured a Backup Plan.
  - Defined Backup Rules and backup schedules.
  - Configured backup retention periods.
  - Selected resources to be protected.

- Studied and performed backups of the following resources:
  - Amazon EC2: Protected the application server and its associated data through the EC2 backup mechanism.
  - Amazon RDS for MySQL: Backed up the database used by the Maiora Fashion Store website.
  - Amazon EBS: Studied volume data protection through EC2 backups or the appropriate EBS backup mechanism.

- Practiced monitoring and verifying backup results:
  - Checked Backup Job statuses.
  - Identified successful and failed backup operations.
  - Inspected Recovery Points stored in the Backup Vault.
  - Identified backup creation timestamps.
  - Verified information about protected resources.

- Studied IAM Roles and the permissions required by AWS Backup:
  - The role of IAM Roles during backup and restoration operations.
  - Trust Relationships that allow AWS Backup to assume an IAM Role.
  - Permissions required for Backup and Restore operations.
  - The `iam:PassRole` permission when restoring resources, where required.

- Understood how Recovery Points can be used to restore application servers and databases when incidents occur.

- Studied the factors affecting AWS Backup costs:
  - Backup data volume.
  - Recovery Point retention periods.
  - Number of stored backups.
  - Related restoration and data transfer operations.

- Completed the configuration and verification of centralized backup mechanisms for EC2 and RDS resources, establishing the foundation for Disaster Recovery implementation and restoration testing in subsequent weeks.
