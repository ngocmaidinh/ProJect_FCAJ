
---
title: "Network and Application Setup"
date: 2026-10-30
weight: 4
chapter: false
pre: " <b>4.4.</b> "
---

## 1. Overview

In this section, we will configure the AWS network infrastructure and deploy the application server for the Maiora Fashion Store system.

The primary infrastructure is deployed in the Singapore Region (`ap-southeast-1`). The VPC provides network isolation, while the EC2 instance hosts the PHP-based web application.

The main tasks include:

- Creating and configuring an Amazon VPC.
- Creating public and private subnets.
- Configuring an Internet Gateway and route tables.
- Creating security groups for the application server.
- Launching an EC2 instance.
- Installing and configuring the web server environment.
- Deploying and verifying the Maiora Fashion Store website.

## 2. Create an Amazon VPC

Amazon Virtual Private Cloud (Amazon VPC) allows us to create an isolated virtual network in AWS.

In this workshop, we create a VPC named `backup-dr-vpc` in the Singapore Region.

### 2.1. VPC configuration

Use the following configuration:

| Parameter | Value |
|---|---|
| Name | backup-dr-vpc |
| Region | Asia Pacific (Singapore) |
| IPv4 CIDR | 10.0.0.0/16 |
| Availability Zones | 2 |
| Public Subnets | 2 |
| Private Subnets | 2 |
| NAT Gateway | Not configured |
| VPC Endpoints | Not configured |

### 2.2. Create the VPC

1. Open the AWS Management Console.
2. Navigate to **VPC**.
3. Select **Your VPCs**.
4. Click **Create VPC**.
5. Enter the VPC name and IPv4 CIDR block.
6. Create the VPC.

![Create AWS VPC](/ProJect_FCAJ/images/4-Workshop/4.4-Network-and-Application-Setup/create-vpc.png)

## 3. Configure Subnets

Subnets divide the VPC network into smaller network segments.

The workshop uses public subnets for the application server and private subnets for internal resources such as the database.

### 3.1. Public subnets

Public subnets are associated with a route table that directs internet-bound traffic through the Internet Gateway.

The EC2 application server is deployed in a public subnet to allow users to access the website.

### 3.2. Private subnets

Private subnets are intended for resources that should not be directly accessible from the public internet.

The Amazon RDS MySQL database is deployed in private subnets.

![VPC Subnet Configuration](/ProJect_FCAJ/images/4-Workshop/4.4-Network-and-Application-Setup/vpc-subnets.png)

## 4. Configure Internet Gateway and Route Tables

### 4.1. Create an Internet Gateway

An Internet Gateway enables communication between resources in public subnets and the internet.

Steps:

1. Open the VPC console.
2. Select **Internet Gateways**.
3. Click **Create internet gateway**.
4. Enter a name, such as `backup-dr-igw`.
5. Attach the Internet Gateway to `backup-dr-vpc`.

### 4.2. Configure the public route table

Configure the public route table with the following route:

| Destination | Target |
|---|---|
| 10.0.0.0/16 | local |
| 0.0.0.0/0 | Internet Gateway |

Associate this route table with the public subnets.

Private subnets do not receive a direct route to the Internet Gateway in this workshop.

![Internet Gateway and Route Table](/ProJect_FCAJ/images/4-Workshop/4.4-Network-and-Application-Setup/internet-gateway-route-table.png)

## 5. Create Security Groups

Security Groups act as virtual firewalls that control inbound and outbound traffic for AWS resources.

### 5.1. Application Security Group

Create a security group named `ec2-sg` for the EC2 application server.

Configure the inbound rules as follows:

| Type | Protocol | Port | Source |
|---|---|---|---|
| SSH | TCP | 22 | Administrator's IP address |
| HTTP | TCP | 80 | 0.0.0.0/0 |
| HTTPS | TCP | 443 | 0.0.0.0/0 |

SSH access should be restricted to trusted administrator IP addresses.

### 5.2. Database Security Group

The RDS database uses a separate security group named `rds-sg`.

Configure the inbound rule:

| Type | Protocol | Port | Source |
|---|---|---|---|
| MySQL/Aurora | TCP | 3306 | EC2 application security group (`ec2-sg`) |

This configuration allows the application server to communicate with the database without exposing the database directly to the internet.

## 6. Launch the EC2 Application Server

Amazon EC2 provides the virtual machine used to host the Maiora Fashion Store website.

### 6.1. EC2 instance configuration

Use the following configuration as a reference:

| Parameter | Value |
|---|---|
| Instance name | app-server |
| Region | Singapore |
| Instance type | t3.micro |
| Operating system | Amazon Linux |
| VPC | backup-dr-vpc |
| Subnet | Public subnet |
| Auto-assign public IP | Enabled |
| Security Group | ec2-sg |

Select or create an appropriate key pair for SSH access.

### 6.2. Launch the instance

1. Open the EC2 console.
2. Select **Instances**.
3. Click **Launch instances**.
4. Enter `app-server` as the instance name.
5. Select an Amazon Linux AMI.
6. Choose the `t3.micro` instance type.
7. Configure the VPC and public subnet.
8. Attach the `ec2-sg` security group.
9. Select the key pair.
10. Launch the instance.

![Launch EC2 Instance](/ProJect_FCAJ/images/4-Workshop/4.4-Network-and-Application-Setup/launch-ec2.png)

## 7. Configure the Web Server Environment

After the EC2 instance is running, connect to it using SSH.

Install and start the Apache web server and PHP environment.

Example commands for Amazon Linux:

```bash
sudo dnf update -y
sudo dnf install -y httpd php php-fpm php-mysqlnd
sudo systemctl enable httpd
sudo systemctl start httpd
sudo systemctl enable php-fpm
sudo systemctl start php-fpm
```

Verify the Apache service:

```bash
sudo systemctl status httpd
```

Verify the PHP version:

```bash
php -v
```

The web server should be running before deploying the application files.

## 8. Deploy the Maiora Fashion Store Website

The Maiora Fashion Store application is developed using PHP and MySQL.

The application files are deployed to the Apache document root:

```bash
/var/www/html
```

The main application components include:

- `index.php`: Homepage.
- `products.php`: Product listing.
- `login.php`: User login.
- `register.php`: User registration.
- `cart.php`: Shopping cart.
- `checkout.php`: Order checkout.
- `orders.php`: Order history.
- `auth.php`: Authentication and session handling.

The database connection configuration is stored separately at:

```bash
/etc/shop/db-config.php
```

This keeps database credentials outside the website's public document root.

Ensure that the application files and configuration have appropriate ownership and permissions.

## 9. Verify the Application

After deploying the application, access the website using the EC2 public IPv4 address or its associated Elastic IP.

Verify the following functions:

- The homepage loads successfully.
- Product information is displayed.
- Product images are loaded from Amazon S3.
- Users can access the login and registration pages.
- The shopping cart interface is displayed.
- The website can access its configured database through the application.

![Maiora Fashion Store Website](/ProJect_FCAJ/images/4-Workshop/4.4-Network-and-Application-Setup/maiora-website.png)

## 10. Expected Results

After completing this section, the following components should be available:

- An Amazon VPC named `backup-dr-vpc`.
- Public and private subnets configured in the Singapore Region.
- An Internet Gateway and public route table.
- Security groups for the EC2 application server and RDS database.
- An EC2 instance named `app-server`.
- Apache and PHP installed and running.
- The Maiora Fashion Store website deployed and accessible.

The infrastructure is now ready for the database and storage configuration described in the next section.
