
---
title: "Week 9 Worklog"
date: 2026-10-05
weight: 9
chapter: false
pre: "<b>1.9.</b>"
---

### Week 9 Objectives:

- Design and simulate potential failure scenarios for the Maiora Fashion Store system.
- Test the recovery of data and resources from backups.
- Evaluate website functionality after restoration.
- Record recovery time and assess Recovery Time Objective (RTO) and Recovery Point Objective (RPO).
- Identify limitations and propose improvements to the Backup and Disaster Recovery solution.

### Tasks to Be Completed This Week:

| Day | Tasks | Start Date | Completion Date | Reference Materials |
|---|---|---|---|---|
| Monday | Design failure scenarios involving data loss, accidental S3 object deletion, and EC2 application server failure. | 05/10/2026 | 05/10/2026 | [AWS Disaster Recovery](https://docs.aws.amazon.com/whitepapers/latest/disaster-recovery-workloads-on-aws/) |
| Tuesday | Inspect S3 Versioning, Delete Markers, and the recovery of product image versions. | 06/10/2026 | 06/10/2026 | [Amazon S3 Versioning](https://docs.aws.amazon.com/AmazonS3/latest/userguide/Versioning.html) |
| Wednesday | Simulate an EC2 application server failure and restore the instance from an AWS Backup Recovery Point. | 07/10/2026 | 08/10/2026 | [AWS Backup Documentation](https://docs.aws.amazon.com/aws-backup/) |
| Friday | Verify RDS status, database contents, and website functionality after restoration. | 09/10/2026 | 09/10/2026 | [Amazon RDS Documentation](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/) |
| Saturday | Record recovery time, determine RTO, and evaluate RPO based on the Recovery Point used. | 10/10/2026 | 10/10/2026 | [AWS Disaster Recovery](https://docs.aws.amazon.com/whitepapers/latest/disaster-recovery-workloads-on-aws/) |

### Week 9 Achievements:

- Designed failure scenarios for the Maiora Fashion Store system:
  - Data loss or accidental data deletion.
  - Amazon EC2 application server failure.
  - Amazon RDS database failure or recovery requirements.
  - Deleted product images or incorrect object versions in Amazon S3.

- Tested the resource restoration process using AWS Backup:
  - Selected an appropriate Recovery Point.
  - Inspected Backup Job and Recovery Point statuses.
  - Restored the EC2 application server.
  - Verified resource status after restoration.
  - Identified configuration changes required to bring the website back online.

- Inspected Amazon S3 data protection and recovery capabilities:
  - Checked the bucket Versioning status.
  - Inspected object versions using the Show versions feature.
  - Studied the Delete Marker mechanism when objects are deleted.
  - Checked the recovery of an appropriate product image version.
  - Studied object replication and deletion behavior between the Singapore and Sydney buckets through Cross-Region Replication.

- Verified the Amazon RDS database after restoration:
  - Checked the DB Instance status.
  - Identified the restored database endpoint.
  - Inspected data used by the Maiora Fashion Store website.
  - Identified the changes required in the PHP application's database connection configuration.

- Evaluated website functionality after restoration:
  - Tested access to the homepage.
  - Checked product listings and product information.
  - Verified product image loading from Amazon S3.
  - Tested relevant application functions.
  - Identified issues caused by changes to endpoints, IP addresses, or resource configurations.

- Studied the role of Amazon CloudWatch in resource monitoring:
  - Monitored EC2 operational metrics.
  - Inspected RDS status and related metrics.
  - Studied the use of CloudWatch Alarms to detect abnormal conditions.
  - Explored integration with notification services when required.

- Recorded recovery time to evaluate Recovery Time Objective (RTO):
  - Identified the incident start time or the beginning of the recovery procedure according to the test scenario.
  - Recorded the time when the resource restoration was completed.
  - Identified when the website became operational and passed the required verification steps.
  - Calculated the total recovery duration based on the recorded timestamps.

- Evaluated Recovery Point Objective (RPO):
  - Identified the incident occurrence time.
  - Determined the timestamp of the Recovery Point used for restoration.
  - Compared the two timestamps to estimate the potential data loss interval.
  - Compared the result with the expected RPO target.

- Compared test results with the defined RTO and RPO objectives, while evaluating how backup retention periods and backup frequency affect data recovery capabilities.

- Identified several limitations of the current solution:
  - EC2 and RDS restoration requires additional configuration steps.
  - Changes to the RDS endpoint may require updates to the application configuration.
  - The Elastic IP may need to be reassociated after EC2 restoration.
  - Replicating S3 data to Sydney does not automatically provide application failover to the secondary Region.
  - Resource restoration may require additional time and incur extra costs.

- Proposed improvements to the system:
  - Maintain suitable Backup Plans and retention policies.
  - Inspect Recovery Points periodically.
  - Perform scheduled restoration tests.
  - Establish a procedure for updating application configurations after restoration.
  - Consider expanding monitoring and recovery automation capabilities in the future.
