
---
title: "Week 7 Worklog"
date: 2026-09-21
weight: 7
chapter: false
pre: "<b>1.7.</b>"
---

### Week 7 Objectives:

- Study Backup and Disaster Recovery architectures across multiple AWS Regions.
- Analyze the disaster recovery approach between Singapore and Sydney.
- Explore data replication mechanisms and resource restoration across Regions.
- Determine a suitable disaster recovery scope for the Maiora Fashion Store system.
- Design the Backup and Disaster Recovery architecture for the system.

### Tasks to Be Completed This Week:

| Day | Tasks | Start Date | Completion Date | Reference Materials |
|---|---|---|---|---|
| Monday | Study Recovery Time Objective (RTO), Recovery Point Objective (RPO), and Disaster Recovery models. | 21/09/2026 | 21/09/2026 | [AWS Cloud Journey](https://cloudjourney.awsstudygroup.com/) |
| Tuesday | Analyze the system architecture with Singapore as the primary Region and Sydney as the secondary Region. | 22/09/2026 | 22/09/2026 | [AWS Cloud Journey](https://cloudjourney.awsstudygroup.com/) |
| Wednesday | Study AWS Backup Cross-Region Copy and Amazon S3 Cross-Region Replication. | 23/09/2026 | 24/09/2026 | [AWS Backup Documentation](https://docs.aws.amazon.com/aws-backup/); [AWS Cloud Journey](https://cloudjourney.awsstudygroup.com/) |
| Friday | Research recovery approaches for EC2, RDS, and S3 data when the primary Region experiences an outage. | 25/09/2026 | 25/09/2026 | [AWS Cloud Journey](https://cloudjourney.awsstudygroup.com/) |
| Saturday | Design the Backup and DR architecture diagram and define the system recovery procedure. | 26/09/2026 | 26/09/2026 | [AWS Cloud Journey](https://cloudjourney.awsstudygroup.com/) |

### Week 7 Achievements:

- Understood Backup and Disaster Recovery architectures deployed across multiple AWS Regions to improve data protection when the primary Region experiences an outage.

- Studied and defined the roles of the two Regions in the architecture:
  - Singapore (`ap-southeast-1`): The primary Region hosting the Maiora Fashion Store website, Amazon EC2 application server, and Amazon RDS for MySQL database.
  - Sydney (`ap-southeast-2`): The secondary Region receiving product image data replicated from the primary S3 bucket through Cross-Region Replication.

- Studied cross-Region data replication and protection mechanisms:
  - AWS Backup Cross-Region Copy: Copies Recovery Points to a Backup Vault in another Region when configured.
  - Amazon S3 Cross-Region Replication (CRR): Automatically replicates eligible S3 objects to a destination bucket in another Region according to replication rules.
  - Recovery Point: Preserves resource data at a specific point in time and serves as a basis for resource restoration.

- Learned the requirements for implementing cross-Region backups:
  - Create a Backup Vault in the destination Region when using AWS Backup Cross-Region Copy.
  - Configure appropriate IAM Roles and access permissions.
  - Define Recovery Point retention policies.
  - Ensure that services and resources in the destination Region meet restoration requirements.
  - Verify replication status and data accessibility in the destination Region.

- Studied services that support system availability and monitoring:
  - Amazon Route 53: Manages DNS and supports traffic routing between endpoints.
  - Amazon CloudWatch: Collects and monitors operational metrics from AWS resources.
  - Amazon SNS: Supports notifications for events and alarms.
  - AWS Elastic Disaster Recovery: Supports server recovery on AWS when failures occur.

- Analyzed recovery approaches for the Maiora Fashion Store components:
  - EC2: Use AWS Backup Recovery Points to restore the application server in an appropriate Region.
  - RDS: Use suitable backups or snapshots to restore the database.
  - S3: Use replicated data in the Sydney destination bucket to support product image access and recovery.

- Defined a general recovery procedure for primary Region failures:
  - Identify the scope and impact of the incident.
  - Select an appropriate Recovery Point.
  - Restore the application server and database.
  - Verify product image data in the secondary Region.
  - Update connection settings and access addresses when necessary.
  - Test website functionality after restoration.

- Designed the Backup and Disaster Recovery architecture for Maiora Fashion Store, illustrating data flows between EC2, RDS, S3, and AWS Backup in the primary Region, together with the replication of product image data to the secondary Region.

- Understood the relationship between implementation costs, Recovery Time Objective (RTO), and Recovery Point Objective (RPO). Recognized that continuously running standby resources can increase costs, while on-demand recovery can reduce costs but requires additional recovery time.

- Defined the actual implementation scope of the project: AWS Backup protects EC2 and RDS resources in Singapore, while S3 Cross-Region Replication copies product image data to Sydney. Restoring EC2 and RDS in another Region is treated as a Disaster Recovery procedure that requires manual recovery steps rather than automatic failover.
