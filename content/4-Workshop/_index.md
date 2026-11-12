
---
title: "Workshop"
date: 2026-11-01
weight: 4
chapter: false
pre: " <b> 4. </b> "
---

# Research and Implementation of a Backup and Disaster Recovery System on Amazon Web Services (AWS)

### Overview

In this workshop, we will learn how to design, implement, and evaluate a Backup and Disaster Recovery (DR) system on Amazon Web Services (AWS) to improve data protection, system availability, and business continuity.

The project uses a fashion e-commerce website named Maiora Fashion Store as the practical application. The system is deployed on AWS, using Amazon EC2 to host the web application, Amazon RDS for MySQL to store application data, and Amazon S3 to store product images.

The architecture is designed with a primary environment in the Asia Pacific (Singapore) Region and a Disaster Recovery environment in the Asia Pacific (Sydney) Region. AWS Backup is used to manage and protect EC2 and RDS resources through centralized backup plans, backup vaults, and recovery points. Amazon S3 Versioning and Cross-Region Replication (CRR) provide additional protection for product images and stored objects.

The workshop also focuses on implementing recovery procedures and simulating common failure scenarios, such as EC2 instance failures, database recovery, and accidental deletion of stored data. Recovery Time Objective (RTO) and Recovery Point Objective (RPO) are measured to evaluate the effectiveness of the implemented Backup and Disaster Recovery solution.

Through this workshop, we will build an AWS-based Backup and Disaster Recovery system, configure backup policies, implement cross-region data protection, perform recovery operations, test failure scenarios, and evaluate the system's recovery capabilities.

### Objectives

- **Backup and Disaster Recovery Architecture:** Design a Backup and DR architecture using AWS services to protect the Maiora Fashion Store application.
- **AWS Network Infrastructure:** Configure Amazon VPC, public and private subnets, route tables, Internet Gateway, and Security Groups.
- **Amazon EC2 Deployment:** Deploy and configure an EC2 instance to host the PHP-based e-commerce website.
- **Amazon RDS Database:** Deploy and configure an Amazon RDS for MySQL database to store application data securely.
- **Amazon S3 Storage Protection:** Store product images in Amazon S3 and configure Versioning and Cross-Region Replication.
- **AWS Backup Configuration:** Create backup vaults, backup plans, and recovery points to protect EC2 and RDS resources.
- **Cross-Region Disaster Recovery:** Configure the primary environment in Singapore and the DR environment in Sydney to support data recovery in another AWS Region.
- **System Recovery and Restoration:** Perform EC2 instance restoration, RDS database restoration, and S3 object recovery.
- **RTO and RPO Evaluation:** Measure recovery time and data recovery points to evaluate the effectiveness of the Backup and DR solution.
- **System Testing and Evaluation:** Simulate system failures, verify data integrity, test application availability, and evaluate recovery results.

### Contents

1. [Backup and Disaster Recovery Architecture Overview](4.1-Workshop-overview/)
2. [Deployment Environment Preparation](4.2-Prerequisite/)
3. [AWS Network Infrastructure Design and Deployment](4.3-AWS-Network-Infrastructure/)
4. [Amazon EC2 Deployment and Website Configuration](4.4-EC2-Security-Groups/)
5. [Amazon RDS Database Deployment and Configuration](4.5-RDS-Database/)
6. [Amazon S3 Storage and Cross-Region Replication Configuration](4.6-S3-Storage-Replication/)
7. [AWS Backup Configuration and Backup Policy Implementation](4.7-AWS-Backup/)
8. [Disaster Recovery Implementation and Resource Restoration](4.8-Disaster-Recovery/)
9. [System Failure Simulation and Recovery Testing](4.9-Recovery-Testing/)
10. [RTO, RPO Evaluation and System Assessment](4.10-RTO-RPO-Evaluation/)
11. [System Verification and AWS Resource Cleanup](4.11-System-Cleanup/)
