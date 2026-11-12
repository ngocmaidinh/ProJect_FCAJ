
---
title: "Backup and Cross-Region Replication"
date: 2026-11-10
weight: 6
chapter: false
pre: "<b> 4.6. </b>"
---

## 4.6. Backup and Cross-Region Replication

In this section, AWS Backup and Amazon S3 Cross-Region Replication are configured to protect the application infrastructure and product images of the Maiora Fashion Store.

AWS Backup is used to create and manage backups of EC2 and RDS resources in the primary AWS Region (Singapore). Amazon S3 Cross-Region Replication (CRR) is used to replicate product images from the Singapore bucket to a destination bucket in Sydney.

### 4.6.1. Creating an AWS Backup Vault

AWS Backup Vault is used to organize and manage recovery points created by backup operations.

A backup vault named `BackupDR-Vault` is used in the Singapore Region to store recovery points for the application resources.

The vault provides a centralized location for managing backup data and supports the restoration process when resources need to be recovered.

![AWS Backup Vault](/ProJect_FCAJ/images/4-Workshop/4.6-Backup-and-Cross-Region-Replication/backup-vault.png)

### 4.6.2. Backing Up EC2 and RDS Resources

AWS Backup is used to create backups of the EC2 application server and the RDS MySQL database.

The protected resources include:

- EC2: the application server hosting the Maiora Fashion Store website.
- RDS: the MySQL database storing application data.

On-demand backup jobs are initiated to create recovery points for the selected resources.

These recovery points provide backup data that can be used to restore the application server or database when necessary.

![AWS Backup Recovery Points](/ProJect_FCAJ/images/4-Workshop/4.6-Backup-and-Cross-Region-Replication/backup-recovery-points.png)

### 4.6.3. Monitoring Backup Jobs

AWS Backup provides backup job information to track the progress and status of backup operations.

The backup job status is checked to verify whether the backup operation has completed successfully.

Important information includes:

- Resource type and resource identifier.
- Backup job status.
- Backup start and completion time.
- Recovery point information.

A completed backup job indicates that AWS Backup has successfully created the corresponding recovery point.

![AWS Backup Job Status](/ProJect_FCAJ/images/4-Workshop/4.6-Backup-and-Cross-Region-Replication/backup-job.png)

### 4.6.4. Enabling Amazon S3 Versioning

Amazon S3 Versioning is enabled on the source bucket in Singapore.

Versioning maintains multiple versions of an object in the same bucket. When an existing object is overwritten or deleted, previous versions can be retained according to the bucket's versioning behavior.

This feature helps protect product images from accidental overwrites or deletions and provides additional recovery options.

![S3 Versioning Configuration](/ProJect_FCAJ/images/4-Workshop/4.6-Backup-and-Cross-Region-Replication/s3-versioning.png)

### 4.6.5. Configuring S3 Cross-Region Replication

Amazon S3 Cross-Region Replication (CRR) is configured to replicate product images from the source bucket in Singapore to a destination bucket in Sydney.

The replication configuration includes:

- Source bucket: `myproject-backup-primary-671657`.
- Source Region: Asia Pacific (Singapore).
- Destination Region: Asia Pacific (Sydney).
- Replication scope: product image objects under the `products/` prefix.
- Replication role: an IAM role authorized to replicate objects between the two buckets.

Both source and destination buckets must have S3 Versioning enabled.

After the replication rule is enabled, eligible new objects uploaded to the source bucket are automatically replicated to the destination bucket. Replication is asynchronous, so the destination object may not appear immediately.

![S3 Cross-Region Replication Rule](/ProJect_FCAJ/images/4-Workshop/4.6-Backup-and-Cross-Region-Replication/s3-replication-rule.png)

### 4.6.6. Verifying Replicated Objects in Sydney

After the replication rule is configured, the destination bucket in Sydney is checked to verify that product images have been replicated.

The destination bucket provides a secondary copy of eligible product image objects in another AWS Region.

This helps improve data availability if the source Region or source bucket becomes unavailable.

Note that S3 Cross-Region Replication does not automatically replicate every historical object uploaded before the replication rule was enabled. Existing objects may require S3 Batch Replication. Replication behavior for delete markers and permanent version deletions also depends on the replication configuration.

![S3 Replicated Objects in Sydney](/ProJect_FCAJ/images/4-Workshop/4.6-Backup-and-Cross-Region-Replication/s3-sydney-replica.png)

### 4.6.7. Section Summary

In this section, AWS Backup and Amazon S3 Cross-Region Replication are configured to protect different parts of the Maiora Fashion Store system.

AWS Backup provides recovery points for the EC2 application server and RDS database, while S3 Cross-Region Replication provides a secondary copy of eligible product images in Sydney.

Together, these mechanisms improve the protection and recoverability of application infrastructure and stored image data.
sted zone](/images/5-Workshop/5.6-Cleanup/delete-zone.png)

2. Disassociate the Route 53 Resolver Rule - myS3Rule from "VPC Onprem" and Delete it. 

![hosted zone](/ProJect_FCAJ/images/5-Workshop/5.6-Cleanup/vpc.png)

4. Open the CloudFormation console  and delete the two CloudFormation Stacks that you created for this lab:
+ PLOnpremSetup
+ PLCloudSetup

![delete stack](/ProJect_FCAJ/images/5-Workshop/5.6-Cleanup/delete-stack.png)

5. Delete S3 buckets
+ Open S3 console
+ Choose the bucket we created for the lab, click and confirm empty. Click delete and confirm delete.

![delete s3](/ProJect_FCAJ/images/5-Workshop/5.6-Cleanup/delete-s3.png)