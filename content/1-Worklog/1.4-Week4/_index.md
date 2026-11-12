
---
title: "Week 4 Worklog"
date: 2026-08-31
weight: 4
chapter: false
pre: "<b>1.4.</b>"
---

### Week 4 Objectives:

- Study Amazon RDS and the MySQL database management system.
- Deploy Amazon RDS for MySQL to store data for the Maiora Fashion Store website.
- Configure secure private connectivity between the EC2 application server and the RDS database.
- Integrate the PHP website with the MySQL database.
- Explore Amazon RDS backup and data protection mechanisms.

### Tasks to Be Completed This Week:

| Day | Tasks | Start Date | Completion Date | Reference Materials |
|---|---|---|---|---|
| Monday | Study Amazon RDS, MySQL, DB Instances, databases, and database backup mechanisms. | 31/08/2026 | 31/08/2026 | [Amazon RDS Documentation](https://docs.aws.amazon.com/rds/) |
| Tuesday | Create an Amazon RDS for MySQL instance, select its configuration, and configure network connectivity within the VPC. | 01/09/2026 | 02/09/2026 | [Amazon RDS Documentation](https://docs.aws.amazon.com/rds/) |
| Thursday | Configure the RDS Security Group and initialize the `shop` database with tables required by the website. | 03/09/2026 | 03/09/2026 | [MySQL Documentation](https://dev.mysql.com/doc/) |
| Friday | Configure PHP on EC2 to connect to RDS using a separate database configuration file. | 04/09/2026 | 04/09/2026 | [PHP Documentation](https://www.php.net/docs.php) |
| Saturday | Verify EC2-to-RDS connectivity, inspect database records, and test product display functionality on the website. | 05/09/2026 | 05/09/2026 | [Amazon RDS Documentation](https://docs.aws.amazon.com/rds/) |

### Week 4 Achievements:

- Understood the role of Amazon RDS in deploying and managing relational databases on AWS.

- Gained knowledge of fundamental database components and concepts:
  - Amazon RDS for MySQL.
  - DB Instance.
  - Database.
  - Table.
  - SQL Query.
  - Database Endpoint.

- Deployed Amazon RDS for MySQL:
  - Created a DB Instance running MySQL.
  - Configured the DB Instance within the `backup-dr-vpc` VPC.
  - Disabled public accessibility (Public Access: No).
  - Configured the `rds-sg` Security Group to control database access.

- Initialized and managed the `shop` database:
  - Created the `shop` database.
  - Created the `users`, `products`, `cart_items`, `orders`, and `order_items` tables.
  - Inserted and queried product records.
  - Inspected database records using SQL statements.
  - Studied the relationships between database tables.

- Established connectivity between the PHP website on EC2 and Amazon RDS:
  - Identified the database endpoint.
  - Configured database connection details in `/etc/shop/db-config.php`.
  - Used a dedicated database account for the application.
  - Configured the Security Group to allow MySQL connections over TCP port 3306 from the EC2 instance's Security Group.
  - Verified the website's ability to retrieve database records.

- Studied Amazon RDS backup and data protection mechanisms:
  - Automated Backups.
  - DB Snapshots.
  - Backup Retention Period.
  - Point-in-Time Recovery (PITR).

- Understood how Amazon EC2 and Amazon RDS work together to build a web application architecture with a centralized database, where the application server and database are deployed separately.

- Completed the database integration with the Maiora Fashion Store website, establishing the foundation for implementing Backup and Disaster Recovery mechanisms in subsequent weeks.
