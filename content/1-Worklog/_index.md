---
title: "Worklog"
date: 2026-08-10
weight: 1
chapter: false
pre: "<b>1.</b>"
---

# Internship Worklog

### Overview

This section presents the worklog of my internship, which was completed over a period of 10 weeks, from August 10, 2026, to October 18, 2026.

During this period, I researched, designed, and implemented a Backup and Disaster Recovery (DR) system on Amazon Web Services (AWS), using Maiora, a fashion e-commerce website, as the practical application.

Alongside the technical implementation, I developed an FCAJ Workshop to document the system architecture, AWS service configurations, deployment procedures, backup strategies, and disaster recovery processes. The workshop covered the implementation lifecycle, from environment preparation and architecture design to backup configuration, resource restoration, and recovery testing.

The weekly activities focused on building the cloud infrastructure, deploying the Maiora website, configuring database and storage services, implementing backup and cross-Region data protection, testing restoration procedures, and preparing the final bilingual workshop documentation.

The main activities completed during the internship are summarized below:

### Weekly Activities

**Week 1:** [Project Introduction and AWS Environment Preparation](1.1-week1/)

Reviewed the internship program, project objectives, and working procedures. Explored the AWS Management Console, AWS CLI, and fundamental AWS services to prepare for the project implementation.

**Week 2:** [System Requirements and Architecture Design](1.2-week2/)

Identified the system requirements, studied Backup and Disaster Recovery concepts, selected appropriate AWS services, and designed the primary and disaster recovery architecture across Singapore and Sydney Regions.

**Week 3:** [Amazon VPC and Network Infrastructure Deployment](1.3-week3/)

Created the Amazon VPC, configured CIDR blocks, public and private subnets, route tables, Internet Gateway, and security groups to establish the network infrastructure.

**Week 4:** [Amazon EC2 and Maiora Web Application Deployment](1.4-week4/)

Launched the EC2 application server, prepared the Amazon Linux environment, installed and configured Apache and PHP, and deployed the Maiora fashion e-commerce website.

**Week 5:** [Amazon RDS and Amazon S3 Configuration](1.5-week5/)

Created and configured the MySQL database using Amazon RDS, connected the application server to the database, configured Amazon S3 for product image storage, and enabled S3 Versioning.

**Week 6:** [AWS Backup and Cross-Region Data Protection](1.6-week6/)

Created an AWS Backup vault and backup plan, configured backup operations for EC2 and RDS resources, examined backup jobs and recovery points, and configured S3 Cross-Region Replication between Singapore and Sydney.

**Week 7:** [Disaster Recovery Environment Preparation](1.7-week7/)

Prepared the disaster recovery environment in the Sydney Region, examined the cross-Region recovery approach, and reviewed the procedures for restoring resources from available backups.

**Week 8:** [Backup Restoration and Data Integrity Verification](1.8-week8/)

Performed resource restoration using AWS Backup recovery points, checked the availability of recovered application resources, and verified the integrity and consistency of restored data.

**Week 9:** [Disaster Recovery Scenarios and Recovery Testing](1.9-week9/)

Performed application and data recovery scenarios, simulated potential system failures, examined the restoration procedures, and verified the availability of recovered application and database resources.

**Week 10:** [Workshop Documentation and Project Completion](1.10-week10/)

Reviewed the AWS architecture and implementation procedures, organized screenshots and technical evidence, completed the bilingual FCAJ Workshop documentation, summarized the implementation and recovery testing results, and finalized the internship report.