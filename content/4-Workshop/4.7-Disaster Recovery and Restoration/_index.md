
---
title: "Disaster Recovery and Restoration"
date: 2026-10-31
weight: 7
chapter: false
pre: "<b>4.7.</b>"
---

## 4.7. Disaster Recovery and Restoration

This section demonstrates the recovery process for the Maiora Fashion Store application when infrastructure or data becomes unavailable.

AWS Backup is used to restore the EC2 application server and the RDS MySQL database from available recovery points. Amazon S3 is also checked to verify that replicated product images remain available in the Sydney Region.

The recovery procedure focuses on restoring application components and verifying that the website can operate correctly after recovery.

### 4.7.1. Selecting an EC2 Recovery Point

When the EC2 application server becomes unavailable or its data needs to be recovered, an available recovery point can be selected from AWS Backup.

The recovery point contains backup data of the EC2 instance at the time the backup was created.

The recovery point is selected based on its resource identifier, creation time, and backup status.

![EC2 Recovery Point](/ProJect_FCAJ/images/4-Workshop/4.7-Disaster-Recovery-and-Restoration/ec2-restore-point.png)

### 4.7.2. Restoring the EC2 Application Server

The EC2 instance is restored through AWS Backup using the selected recovery point.

During the restore process, the required instance configuration and network settings are reviewed before completing the operation.

After the restore job completes, AWS creates the restored EC2 instance. The restored instance is checked in the EC2 console to verify that it is running.

![Restored EC2 Instance](/ProJect_FCAJ/images/4-Workshop/4.7-Disaster-Recovery-and-Restoration/ec2-restored-instance.png)

### 4.7.3. Reassociating the Elastic IP Address

If the original application server uses an Elastic IP address, the address may need to be associated with the restored EC2 instance.

The Elastic IP address is checked in the EC2 console and associated with the restored instance when necessary.

This step allows users to access the website through the same public IP address, provided that the address is available and belongs to the same AWS Region.

![Elastic IP Reassociation](/ProJect_FCAJ/images/4-Workshop/4.7-Disaster-Recovery-and-Restoration/elastic-ip-reassociation.png)

### 4.7.4. Restoring the RDS MySQL Database

The RDS database is restored from an available AWS Backup recovery point or an existing database snapshot.

During the restore process, the database configuration is reviewed, including the DB instance identifier, VPC, subnet group, security group, and database accessibility settings.

AWS RDS creates a new DB instance for the restored database. The application connection configuration must be updated if the restored database has a different endpoint.

![RDS Restore Process](/ProJect_FCAJ/images/4-Workshop/4.7-Disaster-Recovery-and-Restoration/rds-restore.png)

### 4.7.5. Verifying the Restored Database

After the restored RDS instance becomes available, its status and connection configuration are reviewed.

The application database is checked to confirm that the expected data is available.

The database contains the main application tables:

- `users`
- `products`
- `cart_items`
- `orders`
- `order_items`

This verification helps confirm that the database recovery process has restored the required application data.

![Restored Database](/ProJect_FCAJ/images/4-Workshop/4.7-Disaster-Recovery-and-Restoration/restored-database.png)

### 4.7.6. Verifying Product Images in the Sydney Region

The destination S3 bucket in Sydney is checked to confirm that replicated product images remain available.

The objects under the `products/` prefix are reviewed to verify that the expected images are present.

These replicated objects provide an additional copy of eligible product images in a separate AWS Region.

![S3 Recovery in Sydney](/ProJect_FCAJ/images/4-Workshop/4.7-Disaster-Recovery-and-Restoration/s3-sydney-recovery.png)

### 4.7.7. Testing the Recovered Maiora Fashion Store Website

After the EC2 application server and RDS database have been restored and their configurations updated, the Maiora Fashion Store website is accessed for verification.

The following application functions are checked:

- The website homepage loads successfully.
- Product information is displayed.
- Product images can be retrieved from Amazon S3.
- User login and registration pages are accessible.
- Shopping cart and order functions can be accessed.

The verification confirms that the restored application components can work together and provide the main website functions.

![Maiora Website Recovery Test](/ProJect_FCAJ/images/4-Workshop/4.7-Disaster-Recovery-and-Restoration/maiora-recovery-test.png)

### 4.7.8. Section Summary

In this section, the recovery procedures for the EC2 application server and RDS database are demonstrated using available backup recovery points.

The Elastic IP address is reassociated when necessary, and replicated product images are checked in the Sydney Region.

The final website verification confirms whether the restored application infrastructure, database, and image storage can support the main functions of Maiora Fashion Store.
