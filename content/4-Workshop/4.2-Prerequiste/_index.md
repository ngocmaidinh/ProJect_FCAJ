---
title: "Prerequisites"
date: 2026-10-29
weight: 2
chapter: false
pre: " <b>4.2.</b> "
---

### 1. Overview of the Deployment Environment

To deploy a Backup and Disaster Recovery system for the Maiora Fashion Store website, we need to prepare the AWS cloud environment, application infrastructure, database, and storage resources.

The primary environment is deployed in the Singapore Region (ap-southeast-1), where the website runs on an Amazon EC2 instance and uses Amazon RDS for MySQL to store application data. Amazon S3 is used to store product images and website assets.

The Sydney Region (ap-southeast-2) is used as the destination for Amazon S3 Cross-Region Replication. This configuration helps maintain copies of product images in another AWS Region. AWS Backup is used to manage backup and recovery points for supported resources, including Amazon EC2 and Amazon RDS.

### 2. Required Components

- **Amazon Web Services (AWS):** Provides the cloud infrastructure and services required to deploy the application, store data, and implement backup and recovery mechanisms.

- **Amazon VPC:** Provides an isolated network environment for deploying application and database resources. The VPC includes public and private subnets, route tables, an Internet Gateway, and security groups.

- **Amazon EC2:** Hosts the Maiora Fashion Store website using PHP and Apache. The EC2 instance acts as the application server and communicates with the database hosted on Amazon RDS.

- **Amazon RDS for MySQL:** Provides a managed relational database service for storing website information, including customer accounts, product details, shopping carts, and orders.

- **Amazon S3:** Stores product images and website assets. S3 Versioning is used to preserve object versions, while Cross-Region Replication (CRR) replicates objects from the primary bucket in Singapore to a destination bucket in Sydney.

- **AWS Backup:** Provides centralized backup management for supported AWS resources, including Amazon EC2 and Amazon RDS. Backup vaults and recovery points are used to organize and restore protected resources.

- **Administration Computer:** Used to access the AWS Management Console, configure AWS resources, connect to the EC2 instance, manage application files, and verify the website.

#### Images of the Deployment Environment

Image 5.2.1: Amazon VPC and application infrastructure in the Singapore Region.

![AWS VPC Environment](/images/5-Workshop/5.2-Prerequisite/aws-vpc-environment.png)

Image 5.2.2: Maiora Fashion Store website running on Amazon EC2.

![Maiora Fashion Store Website](/images/5-Workshop/5.2-Prerequisite/maiora-website.png)

Image 5.2.3: Amazon S3 buckets configured for cross-region replication.

![Amazon S3 Cross-Region Replication](/images/5-Workshop/5.2-Prerequisite/s3-cross-region-replication.png)

Image 5.2.4: AWS Backup vault and recovery points.

![AWS Backup Vault](/images/5-Workshop/5.2-Prerequisite/aws-backup-vault.png)

### 3. Prerequisites Before Deployment

1. An AWS account with permissions to create and manage the required AWS resources.
2. The Singapore Region (ap-southeast-1) is selected as the primary deployment Region.
3. A VPC with public and private subnets, route tables, an Internet Gateway, and appropriate security groups is prepared.
4. An Amazon EC2 instance is available to host the PHP-based website.
5. An Amazon RDS for MySQL database is created and configured to allow access from the application server.
6. An Amazon S3 bucket is prepared for storing product images, with Versioning enabled.
7. A destination S3 bucket in the Sydney Region (ap-southeast-2) is prepared for Cross-Region Replication.
8. AWS Backup permissions and the required backup configuration are available for protecting Amazon EC2 and Amazon RDS resources.
9. The website application files and database configuration are ready for deployment and verification.
10. An administration computer with an Internet connection and a modern web browser is available to manage AWS resources.

#### Expected Outcome

After completing the preparation stage, we will have an AWS account ready for deployment, a primary application environment in the Singapore Region, and the required database and storage resources.

The destination S3 bucket in the Sydney Region and the necessary AWS Backup configuration will provide the foundation for implementing cross-region object replication and resource backup.

These preparations enable us to proceed with application deployment, database and storage configuration, backup management, and restoration procedures in the following sections.