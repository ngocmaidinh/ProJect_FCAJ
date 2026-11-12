---
title: "Introduction"
date: 2026-11-10
weight: 1
chapter: false
pre: " <b> 5.1. </b> "
---

### 1. Introduction to the Backup and Disaster Recovery System

- **Backup and Disaster Recovery (DR)** is a solution designed to protect application data and maintain service availability when unexpected incidents occur. By implementing backup and recovery mechanisms on AWS, businesses can reduce the risk of data loss and restore essential services when failures happen.

- **Amazon EC2 and Amazon RDS** provide the main application and database infrastructure for the Maiora Fashion Store website. Amazon EC2 hosts the PHP-based web application, while Amazon RDS for MySQL stores customer accounts, product information, shopping carts, and order data.

- **Amazon S3** is used to store product images and other website assets. S3 Versioning helps preserve multiple versions of objects, while Cross-Region Replication (CRR) replicates objects from the primary bucket in Singapore to a destination bucket in Sydney.

- **AWS Backup** provides centralized backup management for supported AWS resources, including Amazon EC2 and Amazon RDS. Backup plans, backup vaults, and recovery points help organize backup operations and support resource restoration when necessary.

### 2. Workshop Overview

In this workshop, you will build and explore a Backup and Disaster Recovery solution for the Maiora Fashion Store website using AWS services across the Singapore and Sydney Regions.

- **"Application Infrastructure"** uses Amazon VPC to provide the network environment for the website. An Amazon EC2 instance is deployed in a public subnet to host the PHP application, while Amazon RDS for MySQL is placed in a private network environment to store application data securely.

- **"Database and Storage Configuration"** uses Amazon RDS for MySQL to manage the website database and Amazon S3 to store product images. S3 Versioning is enabled to preserve object versions, and Cross-Region Replication is configured to replicate objects to a bucket in the Sydney Region.

- **"Backup Management"** uses AWS Backup to create and manage backup plans, backup vaults, and recovery points for Amazon EC2 and Amazon RDS. These backups provide recovery options when application or database resources are damaged or lost.

- **"Disaster Recovery and Restoration"** focuses on restoring AWS resources from available recovery points and verifying the operation of the website after restoration. The workshop also examines the role of S3 object replication in protecting product images across Regions.

Through this workshop, you will practice deploying application infrastructure on AWS, configuring database and object storage, implementing backup mechanisms, setting up cross-region data replication, and performing restoration procedures to improve the data protection and recoverability of the Maiora Fashion Store website.