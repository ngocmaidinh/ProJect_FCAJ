
---
title: "Week 1 Worklog"
date: 2026-08-10
weight: 1
chapter: false
pre: "<b>1.1.</b>"
---

### Week 1 Objectives:

- Get acquainted with members of the First Cloud AI Journey (FCAJ) program.
- Learn about the internship environment, regulations, and working procedures.
- Understand the fundamentals of Amazon Web Services (AWS) and its main cloud service categories.
- Become familiar with AWS Management Console and AWS Command Line Interface (AWS CLI).
- Explore AWS services related to the Backup and Disaster Recovery project.
- Identify the scope and main components of the proposed Maiora Fashion Store system.

### Tasks to Be Completed This Week:

| Day | Tasks | Start Date | Completion Date | Reference Materials |
|---|---|---|---|---|
| Monday | Get acquainted with FCAJ members; learn about internship regulations, the working environment, and working procedures. | 10/08/2026 | 10/08/2026 | Internship Guidelines |
| Tuesday | Study AWS fundamentals and its main service categories: Compute, Storage, Networking, Database, and Security. | 11/08/2026 | 11/08/2026 | [AWS Cloud Journey](https://cloudjourney.awsstudygroup.com/) |
| Wednesday | Become familiar with AWS Management Console, AWS CLI, AWS Regions, and Availability Zones. | 12/08/2026 | 12/08/2026 | [AWS Cloud Journey](https://cloudjourney.awsstudygroup.com/) |
| Thursday | Learn about Amazon EC2, Amazon EBS, AMI, Instance Types, Key Pairs, and Elastic IP addresses. | 13/08/2026 | 14/08/2026 | [AWS Cloud Journey](https://cloudjourney.awsstudygroup.com/) |
| Saturday | Study IAM, Amazon S3, Amazon RDS, AWS Backup, and the fundamental concepts of Backup and Disaster Recovery. | 15/08/2026 | 15/08/2026 | [AWS Cloud Journey](https://cloudjourney.awsstudygroup.com/) |

### Week 1 Achievements:

- Became familiar with FCAJ members and understood the program's regulations and working procedures.

- Gained an overview of Amazon Web Services (AWS) and its main service categories:
  - Compute.
  - Storage.
  - Networking.
  - Database.
  - Security.

- Became familiar with AWS management tools and concepts:
  - AWS Management Console.
  - AWS Command Line Interface (AWS CLI).
  - AWS Region.
  - Availability Zone.

- Studied AWS services related to the project:
  - Amazon EC2: Provides virtual servers for hosting the website.
  - Amazon EBS: Provides block storage for EC2 instances.
  - Amazon RDS: Provides a managed relational database service.
  - Amazon S3: Stores product images and object data.
  - AWS Backup: Manages and performs backups of AWS resources.
  - IAM: Manages identities, roles, and access permissions for AWS services.

- Understood the fundamental concepts:
  - Backup: Creating copies of data and system resources.
  - Recovery Point: A point in time to which a resource can be restored from a backup.
  - Restore: Recovering resources from backups.
  - Disaster Recovery: Restoring systems after an unexpected incident.
  - RPO (Recovery Point Objective): The target point in time to which data must be recovered.
  - RTO (Recovery Time Objective): The target duration required to restore a system after an incident.

- Identified the proposed application model as the Maiora Fashion Store e-commerce website, using EC2 as the application server, RDS for MySQL as the database, and S3 for product image storage.

- Initially identified the system architecture with Singapore (`ap-southeast-1`) as the primary Region and Sydney (`ap-southeast-2`) as the secondary Region, providing the foundation for implementing backup and data protection mechanisms in subsequent weeks.
