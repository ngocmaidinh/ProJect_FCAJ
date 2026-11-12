
---
title: "Workshop"
date: 2026-11-01
weight: 4
chapter: false
pre: "<b>4.</b>"
---

# Design and Implementation of a Backup and Disaster Recovery System on Amazon Web Services (AWS)

### Overview

This workshop focuses on designing, implementing, and testing a Backup and Disaster Recovery (DR) system on Amazon Web Services (AWS). The project uses a fashion e-commerce website named Maiora as a practical application to demonstrate data protection, backup management, and system recovery in a cloud environment.

The system is deployed across two AWS Regions: Singapore (ap-southeast-1) as the primary environment and Sydney (ap-southeast-2) as the Disaster Recovery environment. The application runs on Amazon EC2, while Amazon RDS for MySQL stores product information, customer accounts, shopping carts, and order data.

Amazon S3 is used to store product images. S3 Versioning and Cross-Region Replication (CRR) help protect image data and maintain a copy in the secondary Region. AWS Backup is configured to manage backup plans, backup vaults, and recovery points for supported resources.

Through this workshop, we will prepare the AWS environment, deploy the application and database, configure storage and backup services, and perform recovery operations. We will also simulate system failures and evaluate the recovery process using Recovery Time Objective (RTO) and Recovery Point Objective (RPO).

### Objectives

- **AWS Cloud Infrastructure:** Prepare the AWS environment and configure the required network infrastructure using Amazon VPC, subnets, route tables, and security groups.
- **Amazon EC2 Deployment:** Deploy and configure an EC2 instance to host the Maiora fashion e-commerce website.
- **Database Configuration:** Set up Amazon RDS for MySQL and configure secure connectivity between the application server and the database.
- **Amazon S3 Storage:** Store product images in Amazon S3 and configure bucket settings to support application access and data protection.
- **S3 Versioning and Cross-Region Replication:** Enable object versioning and configure replication between the Singapore and Sydney Regions.
- **AWS Backup Configuration:** Create a backup vault and backup plan, configure resource assignments, and generate recovery points for supported AWS resources.
- **Disaster Recovery and Restoration:** Restore EC2 and RDS resources from backup recovery points and verify application and database recovery.
- **System Testing and Evaluation:** Simulate failure scenarios, verify recovered data, and evaluate system recovery performance based on RTO and RPO.
- **Monitoring and Resource Management:** Review system operation, backup status, recovery results, and clean up resources when testing is complete.

### Workshop Contents

1. [Workshop Overview](4.1-Workshop-overview/)
2. [Prerequisites and Environment Preparation](4.2-Prerequiste/)
3. [AWS Architecture Design](4.3-Architecture-Design/)
4. [Network and Application Setup](4.4-Network and Application Setup/)
5. [Database and Storage Configuration](4.5-Database and Storage Configuration/)
6. [Backup and Cross-Region Replication](4.6-Backup and Cross-Region Replication/)
7. [Disaster Recovery and Restoration](4.7-Disaster Recovery and Restoration/)
8. [Testing, Monitoring and Cleanup](4.8-Testing, Monitoring and Cleanup/)
