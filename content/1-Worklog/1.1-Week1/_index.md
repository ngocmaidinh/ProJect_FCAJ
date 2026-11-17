---
title: "Week 1 Worklog"
date: 2026-08-10
weight: 1
chapter: false
pre: "<b>1.1.</b>"
---

### Week 1 Objectives:

- Get acquainted with the members of the First Cloud AI Journey (FCAJ) program.
- Learn about the internship environment, regulations, and working procedures.
- Gain an overview of Amazon Web Services (AWS) and its main cloud service categories.
- Become familiar with the AWS Management Console and AWS Command Line Interface (AWS CLI).
- Explore AWS services related to the Backup and Disaster Recovery project.
- Define the scope and main components of the proposed Maiora Fashion Store system.

### Tasks to Be Completed During This Week:

| Day | Tasks | Start Date | Completion Date | References |
|---|---|---|---|---|
| Monday | Get acquainted with FCAJ members; learn about the internship regulations, working environment, and procedures. | 10/08/2026 | 10/08/2026 | Internship Guidelines |
| Tuesday | Learn about AWS fundamentals and its main service categories: Compute, Storage, Networking, Database, and Security. | 11/08/2026 | 11/08/2026 | [AWS Cloud Journey](https://cloudjourney.awsstudygroup.com/) |
| Wednesday | Become familiar with the AWS Management Console, AWS CLI, AWS Regions, and Availability Zones. | 12/08/2026 | 12/08/2026 | [AWS Cloud Journey](https://cloudjourney.awsstudygroup.com/) |
| Thursday | Explore Amazon EC2, Amazon EBS, AMIs, Instance Types, Key Pairs, and Elastic IP addresses. | 13/08/2026 | 14/08/2026 | [AWS Cloud Journey](https://cloudjourney.awsstudygroup.com/) |
| Friday | Learn about IAM, Amazon S3, Amazon RDS, AWS Backup, and fundamental Backup and Disaster Recovery concepts. | 15/08/2026 | 15/08/2026 | [AWS Cloud Journey](https://cloudjourney.awsstudygroup.com/) |

### Week 1 Achievements:

- Became acquainted with FCAJ members and gained an understanding of the program's regulations and working procedures.

- Gained an overview of Amazon Web Services (AWS) and its main service categories:
  - Compute.
  - Storage.
  - Networking.
  - Database.
  - Security.

- Became familiar with AWS management tools and fundamental concepts:
  - AWS Management Console.
  - AWS Command Line Interface (AWS CLI).
  - AWS Region.
  - Availability Zone.

- Explored AWS services related to the project:
  - Amazon EC2: Provides virtual servers for hosting and running the website.
  - Amazon EBS: Provides block storage volumes for EC2 instances.
  - Amazon RDS: A managed relational database service.
  - Amazon S3: Stores product images and other object data.
  - AWS Backup: Provides centralized management and automated backup of AWS resources.
  - IAM: Manages identities, roles, and access permissions for AWS services.

- Gained an understanding of fundamental Backup and Disaster Recovery concepts:
  - Backup: The process of creating copies of data and system resources to protect against potential failures or data loss.
  - Recovery Point: A point in time to which data or system resources can be restored from a backup.
  - Restore: The process of recovering data or system resources from a backup.
  - Disaster Recovery: The process of restoring system operations after a disaster or unexpected failure.
  - Cross-Region Replication (CRR): A mechanism for replicating data across different AWS Regions to improve data protection and availability.

- Identified the proposed application model as the Maiora Fashion Store e-commerce website, using Amazon EC2 as the application server, Amazon RDS MySQL as the database, and Amazon S3 for product image storage.

- Initially defined the system architecture with Singapore (ap-southeast-1) as the primary Region and Sydney (ap-southeast-2) as the disaster recovery Region. This architecture will support the implementation of backup mechanisms, cross-Region data replication, and resource recovery in the following weeks.