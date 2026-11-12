---
title: "Week 10 Worklog"
date: 2026-10-12
weight: 10
chapter: false
pre: "<b>1.10.</b>"
---

### Week 10 Objectives:

- Review and finalize the Backup and Disaster Recovery system configurations.
- Consolidate the system architecture, implementation procedures, and testing results.
- Review the effectiveness of backup, restoration, and cross-Region data protection mechanisms.
- Complete the internship report and technical documentation for the graduation thesis.
- Finalize the FCAJ Workshop documentation in English and Vietnamese.
- Summarize the project implementation process and the knowledge and skills acquired during the internship.

### Tasks to Be Completed This Week:

| Day | Tasks | Start Date | Completion Date |
|---|---|---|---|
| Monday | Review the architecture, configurations, and status of AWS resources in the system. | 12/10/2026 | 12/10/2026 |
| Tuesday | Consolidate architecture diagrams, evidence screenshots, and implementation and testing results. | 13/10/2026 | 13/10/2026 |
| Wednesday | Review backup and restoration results, verify the simulated failure scenarios, and identify system limitations. | 14/10/2026 | 15/10/2026 |
| Friday | Write, edit, and review the internship report and technical documentation. | 16/10/2026 | 16/10/2026 |
| Sunday | Perform the final review, complete the bilingual workshop documentation, and summarize the internship. | 18/10/2026 | 18/10/2026 |

### Week 10 Achievements:

- Reviewed and consolidated the Backup and Disaster Recovery architecture for the Maiora Fashion Store website using the following main AWS services:
  - Amazon VPC: Provides the network environment and separates public and private subnets.
  - Amazon EC2: Hosts the website application server.
  - Amazon EBS: Provides storage volumes for the EC2 instance.
  - Amazon RDS for MySQL: Stores the website database.
  - Amazon S3: Stores product images and uses Versioning and Cross-Region Replication.
  - AWS Backup: Manages backup operations and stores Recovery Points for EC2 and RDS.

- Reviewed the roles of security and access management services:
  - AWS IAM: Manages users, roles, and resource permissions.
  - Security Groups: Control inbound and outbound network traffic for EC2 and RDS.
  - S3 Bucket Policies: Manage access permissions for objects in S3 buckets.
  - IAM Roles: Provide the permissions required by AWS services to perform backup and restoration operations.

- Reviewed additional AWS services related to monitoring and disaster recovery:
  - Amazon CloudWatch: Monitors AWS resource metrics and statuses.
  - Amazon SNS: Supports notifications for events and alarms.
  - Amazon Route 53: Manages DNS and supports traffic routing.
  - AWS Elastic Disaster Recovery: Provides server recovery capabilities for disaster recovery scenarios.

- Finalized and reviewed the system architecture diagrams:
  - VPC network architecture and website deployment components.
  - Connection flow between EC2 and RDS.
  - Product image access flow from Amazon S3.
  - Backup and Recovery Point creation using AWS Backup.
  - EC2 application server and RDS database restoration procedures.
  - Product image replication from Singapore (`ap-southeast-1`) to Sydney (`ap-southeast-2`) through S3 Cross-Region Replication.

- Consolidated implementation evidence and testing results:
  - VPC, subnet, route table, and Security Group configurations.
  - EC2 instance and RDS database statuses.
  - AWS Backup configuration and status.
  - Backup Jobs and Recovery Points.
  - EC2 and RDS restoration results.
  - S3 Versioning and Cross-Region Replication configurations.
  - Website functionality verification after restoration.

- Reviewed the backup and recovery results:
  - Examined the available Recovery Points for EC2 and RDS resources.
  - Reviewed the restoration procedures and configurations required after recovery.
  - Verified the availability of the restored application server.
  - Checked database connectivity and website functionality after restoration.
  - Reviewed the recovery of product images using S3 Versioning.
  - Examined the role of Cross-Region Replication in protecting product image data across AWS Regions.

- Evaluated the advantages of the system:
  - Centralized backup management for EC2 and RDS through AWS Backup.
  - Recovery Points provide a basis for restoring resources after failures.
  - S3 Versioning supports the recovery of previous object versions.
  - S3 Cross-Region Replication helps protect product image data in another Region.
  - Separating the application server and database improves resource management and access control.

- Reviewed system limitations and operational costs:
  - EC2 and RDS restoration still requires additional configuration steps.
  - Automatic failover of the entire website to Sydney has not been implemented.
  - Restoration may involve additional configuration steps and resource costs.
  - Recovery Point retention, storage capacity, and data transfer costs must be managed.
  - Periodic recovery testing is necessary to ensure backups are usable when required.

- Completed the internship report and technical documentation:
  - Reviewed the content of all report chapters.
  - Added architecture diagrams, configuration screenshots, and testing results.
  - Standardized tables, AWS terminology, and document formatting.
  - Consolidated reference materials.
  - Completed the documentation supporting the graduation thesis titled "Design and Implementation of a Backup and Disaster Recovery System on Amazon Web Services (AWS)".

- Completed the FCAJ Workshop documentation:
  - Organized the workshop into structured sections.
  - Prepared implementation instructions and AWS configuration procedures.
  - Added screenshots illustrating the deployment and configuration process.
  - Reviewed and completed the English and Vietnamese documentation.
  - Checked the navigation structure and presentation of workshop content.

- Summarized the internship experience:
  - Strengthened knowledge of cloud computing and AWS services.
  - Improved skills in configuring, deploying, and managing AWS resources.
  - Gained a better understanding of backup, restoration, and Disaster Recovery testing procedures.
  - Improved skills in troubleshooting, interpreting resource statuses, and preparing technical documentation.