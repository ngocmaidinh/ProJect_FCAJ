
---
title: "Proposal"
date: 2026-11-12
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

# DESIGN AND IMPLEMENTATION OF A BACKUP AND DISASTER RECOVERY SYSTEM ON AMAZON WEB SERVICES (AWS)

## 1. Project Overview

This project focuses on designing and implementing a Backup and Disaster Recovery (DR) system on the Amazon Web Services (AWS) platform for the Maiora Fashion Store e-commerce website.

The system uses AWS services such as Amazon EC2, Amazon RDS, Amazon S3, and AWS Backup to protect application servers, databases, and product image data. In addition, Amazon S3 Cross-Region Replication is used to replicate product image data from the Singapore Region to the Sydney Region, enhancing data protection in the event of an incident affecting the primary Region.

Through system deployment and recovery testing, the project evaluates the system's recovery capabilities and proposes improvements to enhance availability, data security, and website continuity.

## 2. Problem Statement

In an e-commerce environment, product information, customer details, order records, and product images play an important role in business operations. Data loss or server interruptions can prevent a website from operating normally, affecting user experience and order management activities.

Potential incidents include:

- Amazon EC2 instance failures or accidental deletion.
- Amazon RDS database data loss or connectivity failures.
- Product images being deleted or overwritten in Amazon S3.
- Incidents in the primary Region that interrupt access to resources.
- Incorrect changes to application or database configurations.

Without an appropriate backup and recovery mechanism, system restoration may take a significant amount of time, and important data may be lost.

Therefore, implementing a Backup and Disaster Recovery system on AWS is necessary to protect data, support resource restoration, and minimize the impact of unexpected incidents.

## 3. Proposed Solution Architecture

### 3.1. Architecture Model

The system is deployed across two AWS Regions:

- Primary Region: Asia Pacific (Singapore) - `ap-southeast-1`.
- Secondary Region: Asia Pacific (Sydney) - `ap-southeast-2`.

In the Singapore Region, the Maiora Fashion Store website is deployed on Amazon EC2, Amazon RDS for MySQL is used to store application data, and Amazon S3 is used to store product images.

AWS Backup is used to create and manage recovery points for EC2 and RDS resources. For product image data, Amazon S3 Versioning combined with Cross-Region Replication helps retain different object versions and replicate data to the Sydney Region.

### 3.2. Main Components

- Amazon VPC: Provides an isolated network environment for the system, including Public Subnets and Private Subnets.
- Amazon EC2: Hosts the application server running Amazon Linux, Apache, and PHP.
- Amazon RDS for MySQL: Stores the `shop` database, including user, product, shopping cart, and order information.
- Amazon S3: Stores product images used by the website.
- Amazon S3 Versioning: Retains multiple versions of objects to support recovery when data is overwritten or deleted.
- Amazon S3 Cross-Region Replication: Replicates eligible product image objects from the Singapore bucket to the Sydney bucket according to the configured replication rules.
- AWS Backup: Manages backup plans, Backup Vaults, and Recovery Points for supported resources.
- Amazon CloudWatch: Supports resource monitoring and activity tracking when configured.

### 3.3. Operating Principles

Users access the website through the Amazon EC2 application server. The EC2 instance connects to Amazon RDS for MySQL to retrieve and update application data. Product images are stored in Amazon S3 and accessed by the website through object URLs.

AWS Backup protects selected resources and creates Recovery Points for restoration purposes. When an incident occurs, administrators can select an appropriate Recovery Point to restore EC2 or RDS resources.

For product image data, S3 Versioning allows previous object versions to be retrieved. Cross-Region Replication supports the replication of eligible objects to the Sydney bucket.

Resource restoration and service switching are performed manually by administrators within the scope of this implementation.

### 3.4. Architecture Diagram

![AWS Backup and Disaster Recovery Architecture](/ProJect_FCAJ/images/2-Proposal/bdr_architecture.png)

## 4. Technical Implementation Scope

The project focuses on the following implementation activities:

### 4.1. Network Infrastructure Design and Configuration

- Create an Amazon VPC with the CIDR block `10.0.0.0/16`.
- Divide the network into Public Subnets and Private Subnets.
- Configure the Internet Gateway and Route Tables.
- Configure Security Groups to control network traffic.
- Deploy EC2 in a Public Subnet and configure connectivity to RDS in a Private Subnet.

### 4.2. Application Server Deployment

- Launch an EC2 instance running Amazon Linux.
- Install and configure Apache and PHP.
- Deploy the Maiora Fashion Store e-commerce website.
- Verify website accessibility and the operation of its main functions.

### 4.3. Database and Storage Configuration

- Create an Amazon RDS for MySQL instance.
- Initialize the `shop` database.
- Configure connectivity from EC2 to RDS through Security Groups.
- Create an Amazon S3 bucket to store product images.
- Enable S3 Versioning to protect different versions of stored objects.
- Configure Cross-Region Replication from Singapore to Sydney.

### 4.4. Backup System Implementation

- Create an AWS Backup Vault.
- Configure a Backup Plan and Backup Rules.
- Select EC2 and RDS resources for backup.
- Execute Backup Jobs.
- Verify backup job statuses and generated Recovery Points.

### 4.5. Disaster Recovery and Restoration Testing

- Restore the EC2 instance from a Recovery Point.
- Restore the RDS database from a backup.
- Verify application-to-database connectivity after restoration.
- Test website accessibility.
- Test product image recovery using S3 Versioning.
- Verify replicated data in the Sydney Region.

### 4.6. System Testing and Evaluation

- Verify website functionality after deployment.
- Simulate application server failure scenarios.
- Simulate accidental data deletion or modification.
- Perform resource restoration using Recovery Points.
- Evaluate restoration results and identify limitations of the implemented model.

## 5. Implementation Roadmap and Milestones

| Phase | Activities | Expected Results |
|---|---|---|
| Phase 1 | Study AWS and Backup and Disaster Recovery services | Identify the technologies to be used |
| Phase 2 | Design the architecture and configure VPC | Complete the network infrastructure |
| Phase 3 | Deploy EC2 and the website | Website becomes operational |
| Phase 4 | Configure RDS and S3 | Complete the data storage environment |
| Phase 5 | Configure AWS Backup and S3 Replication | Establish data protection mechanisms |
| Phase 6 | Perform restoration and testing | Evaluate recovery capabilities |
| Phase 7 | Consolidate results and complete the report | Complete the project |

## 6. Estimated Budget

The AWS services used in this project may incur costs depending on resource runtime, storage capacity, the number of backups, and data transfer volume.

The main components that may generate costs include:

- Amazon EC2: Costs for the compute instance and EBS storage.
- Amazon RDS: Costs for the DB instance, storage capacity, and backups.
- Amazon S3: Costs for object storage, Versioning, and access requests.
- AWS Backup: Costs for backup storage and related operations.
- Cross-Region Replication: Costs for replication requests and data transfer between Regions.
- Network services: Potential charges for data transfer and network resources.

To control the budget, the system is deployed within a testing environment. Unnecessary resources will be stopped or deleted after testing is completed. Backups and data required for evaluation will be retained according to the project requirements.

## 7. Risk Assessment and Mitigation

| Risk | Impact | Mitigation |
|---|---|---|
| EC2 instance failure or accidental deletion | Website becomes unavailable | Restore EC2 from AWS Backup |
| RDS becomes inaccessible | Website cannot retrieve database records | Restore RDS from a Recovery Point and update the endpoint if necessary |
| Product images are deleted | Product images become unavailable on the website | Use S3 Versioning or replicated data |
| Data is overwritten | Stored content becomes incorrect | Retrieve a previous object version |
| Primary Region failure | Resources in the primary Region become inaccessible | Use replicated data in the Sydney Region and perform the appropriate recovery procedures |
| Incorrect IAM configuration | Backup or Restore operations fail | Verify IAM Roles, Trust Relationships, and required permissions |

The current implementation does not provide automatic failover of the entire system to the Sydney Region. EC2 and RDS restoration, as well as application configuration updates, are performed manually. This limitation must be considered when evaluating the proposed solution.

## 8. Expected Outcomes

Upon completion, the project is expected to achieve the following results:

- Build an AWS infrastructure environment for the Maiora Fashion Store website.
- Successfully deploy the website using EC2, RDS for MySQL, and S3.
- Establish backup mechanisms for EC2 and RDS using AWS Backup.
- Create and manage Recovery Points for resource restoration.
- Configure S3 Versioning and Cross-Region Replication to improve product image data protection.
- Perform application server and database restoration from backups.
- Test selected data loss and service interruption scenarios.
- Evaluate the advantages, limitations, and future development directions of the AWS Backup and Disaster Recovery model.

Through this project, the implementation applies knowledge of cloud computing, infrastructure management, data storage, backup, and system recovery to a practical application environment.
