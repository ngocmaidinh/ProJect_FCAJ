
---
title: "Workshop"
date: 2026-11-01
weight: 4
chapter: false
pre: " <b> 4. </b> "
---

# Research and Implementation of a Backup and Disaster Recovery System on Amazon Web Services (AWS)

### Overview

In this workshop, we will explore the design and implementation of a Backup and Disaster Recovery (DR) system on Amazon Web Services (AWS) for the Maiora Fashion Store website.

The system is deployed primarily in the Singapore Region (ap-southeast-1), where Amazon EC2 hosts the PHP-based website and Amazon RDS for MySQL stores application data, including customer accounts, product information, shopping carts, and orders. Amazon S3 is used to store product images and other website assets.

To improve data protection, Amazon S3 Versioning is enabled to preserve multiple versions of objects. Cross-Region Replication (CRR) is configured to replicate product images from the primary S3 bucket in Singapore to a destination bucket in the Sydney Region (ap-southeast-2).

In addition, AWS Backup is used as a centralized backup management service to protect supported resources, including Amazon EC2 and Amazon RDS. Backup vaults and recovery points provide the foundation for restoring application infrastructure and database resources when failures or data loss occur.

Through this workshop, we will practice preparing the AWS environment, deploying the application, configuring database and storage services, implementing backup mechanisms, and performing recovery tests to verify the integrity and availability of the website and its data.

The main topics include:

- **AWS Architecture Design:** Design the backup and disaster recovery architecture for the Maiora Fashion Store website using AWS services.
- **AWS Network Infrastructure:** Create and configure Amazon VPC, public and private subnets, route tables, Internet Gateway, and Security Groups.
- **Application Deployment on Amazon EC2:** Deploy and configure the PHP-based Maiora Fashion Store website using Apache on an EC2 instance.
- **Database Configuration:** Configure Amazon RDS for MySQL and establish secure connectivity between the application server and the database.
- **Amazon S3 Storage and Replication:** Store product images, enable S3 Versioning, and configure Cross-Region Replication between Singapore and Sydney.
- **Backup Management with AWS Backup:** Create backup vaults and backup plans, protect EC2 and RDS resources, and manage recovery points.
- **Disaster Recovery and Restoration:** Perform restoration procedures for EC2 and RDS resources and verify the recovered application and database.
- **System Testing and Resource Cleanup:** Test backup and recovery operations, verify website functionality and data integrity, and clean up AWS resources when necessary.

### Contents

1. [Workshop Overview](4.1-Workshop-overview/)
2. [Prerequisites](4.2-Prerequisite/)
3. [Architecture Design](4.3-Architecture-Design/)
4. [AWS Network Infrastructure Deployment](4.4-AWS-Network-Infrastructure/)
5. [Maiora Fashion Store Deployment on Amazon EC2](4.5-EC2-Website-Deployment/)
6. [Amazon RDS Database Configuration](4.6-RDS-Database-Configuration/)
7. [Amazon S3 Storage and Cross-Region Replication](4.7-S3-Storage-Replication/)
8. [AWS Backup Configuration and Management](4.8-AWS-Backup-Configuration/)
9. [Disaster Recovery and Restoration Testing](4.9-Disaster-Recovery-Testing/)
10. [System Verification and AWS Resource Cleanup](4.10-System-Verification-Cleanup/)
