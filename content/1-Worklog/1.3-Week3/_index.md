
---
title: "Week 3 Worklog"
date: 2026-08-24
weight: 3
chapter: false
pre: "<b>1.3.</b>"
---

### Week 3 Objectives:

- Learn the Linux environment and basic EC2 server administration operations.
- Install and configure the web server environment on Amazon Linux.
- Understand Apache HTTP Server, PHP, and PHP-FPM.
- Develop and deploy the Maiora Fashion Store e-commerce website.
- Test website accessibility and troubleshoot basic deployment issues.

### Tasks to Be Completed This Week:

| Day | Tasks | Start Date | Completion Date | Reference Materials |
|---|---|---|---|---|
| Monday | Study Amazon Linux, file systems, access permissions, and basic Linux administration commands. | 24/08/2026 | 24/08/2026 | [AWS Cloud Journey](https://cloudjourney.awsstudygroup.com/) |
| Tuesday | Install and configure Apache HTTP Server on EC2; learn how to manage services using systemctl. | 25/08/2026 | 25/08/2026 | [AWS Cloud Journey](https://cloudjourney.awsstudygroup.com/) |
| Wednesday - Thursday | Install PHP, PHP-FPM, and the required components to run PHP applications. | 26/08/2026 | 27/08/2026 | [AWS Cloud Journey](https://cloudjourney.awsstudygroup.com/) |
| Friday | Develop and deploy the Maiora Fashion Store interface using PHP; create product pages and basic website functions. | 28/08/2026 | 28/08/2026 | [AWS Cloud Journey](https://cloudjourney.awsstudygroup.com/) |
| Saturday | Test the website through a web browser, check Apache services, and troubleshoot issues during deployment. | 29/08/2026 | 29/08/2026 | [AWS Cloud Journey](https://cloudjourney.awsstudygroup.com/) |

### Week 3 Achievements:

- Understood how to deploy a web application on Amazon EC2 using the Amazon Linux operating system.

- Became familiar with Linux server administration:
  - Managing files and directories.
  - Checking and modifying access permissions.
  - Using basic administration commands.
  - Checking service status with systemctl.
  - Reviewing system logs and troubleshooting basic errors.

- Installed and configured the web server environment:
  - Amazon Linux.
  - Apache HTTP Server.
  - PHP.
  - PHP-FPM.

- Developed and deployed the Maiora Fashion Store e-commerce website:
  - Created the homepage interface.
  - Developed the product listing page.
  - Created user registration and login pages.
  - Implemented shopping cart functionality.
  - Implemented order placement and order viewing functions.
  - Organized the PHP application source code and components.

- Configured Security Groups to allow the required network connections:
  - SSH (TCP 22) for server administration.
  - HTTP (TCP 80) for website access.
  - HTTPS (TCP 443) when an SSL/TLS certificate is deployed.

- Verified web server operations:
  - Checked the Apache service status.
  - Verified PHP and PHP-FPM.
  - Accessed the website through the EC2 public IPv4 address.
  - Tested the website interface and basic functions.

- Understood the roles of the main components in the web application architecture:
  - Amazon EC2: Provides the environment for running the application.
  - Apache: Receives and processes HTTP requests.
  - PHP: Handles the website's business logic.
  - PHP-FPM: Manages PHP execution processes.

- Completed the initial deployment of Maiora Fashion Store on EC2, establishing the foundation for integrating Amazon RDS as the database and Amazon S3 for product image storage in the following week.
