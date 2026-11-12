
---
title: "Week 2 Worklog"
date: 2026-08-17
weight: 2
chapter: false
pre: "<b>1.2.</b>"
---

### Week 2 Objectives:

- Understand AWS networking architecture and its infrastructure components.
- Design and deploy an Amazon VPC for the Maiora Fashion Store system.
- Configure Public Subnets, Private Subnets, Internet Gateway, and Route Tables.
- Understand network traffic control mechanisms using Security Groups and Network ACLs.
- Deploy Amazon EC2 as the application server for the website.
- Verify network connectivity and EC2 instance accessibility.

### Tasks to Be Completed This Week:

| Day | Tasks | Start Date | Completion Date | Reference Materials |
|---|---|---|---|---|
| Monday | Study Amazon VPC, CIDR, Availability Zones, Public Subnets, Private Subnets, and Route Tables. | 17/08/2026 | 17/08/2026 | [AWS Cloud Journey](https://cloudjourney.awsstudygroup.com/) |
| Tuesday | Study Internet Gateway, Security Groups, and Network ACLs; understand their network traffic control mechanisms. | 18/08/2026 | 18/08/2026 | [AWS Cloud Journey](https://cloudjourney.awsstudygroup.com/) |
| Wednesday | Create the `backup-dr-vpc` VPC, configure the `10.0.0.0/16` CIDR block, and divide the network into Public and Private Subnets. | 19/08/2026 | 20/08/2026 | [AWS Cloud Journey](https://cloudjourney.awsstudygroup.com/) |
| Friday | Configure the Internet Gateway, Route Tables, and Security Groups; launch an EC2 instance as the application server. | 21/08/2026 | 21/08/2026 | [AWS Cloud Journey](https://cloudjourney.awsstudygroup.com/) |
| Saturday | Create a Key Pair, connect to EC2 through SSH, and verify the instance status, IP address, and network accessibility. | 22/08/2026 | 22/08/2026 | [AWS Cloud Journey](https://cloudjourney.awsstudygroup.com/) |

### Week 2 Achievements:

- Understood AWS networking architecture and the role of Amazon VPC in providing an isolated network environment for the system.

- Gained knowledge of the fundamental networking components:
  - Amazon VPC.
  - CIDR Block.
  - Availability Zone.
  - Public Subnet.
  - Private Subnet.
  - Route Table.
  - Internet Gateway.

- Understood network traffic control mechanisms:
  - Security Groups: Control inbound and outbound traffic at the Elastic Network Interface or EC2 instance level.
  - Network ACLs: Control inbound and outbound traffic at the subnet level.

- Designed and deployed the VPC for the system:
  - Created a VPC named `backup-dr-vpc`.
  - Configured the IP address range `10.0.0.0/16`.
  - Created two Public Subnets and two Private Subnets across two Availability Zones.
  - Configured the Internet Gateway and corresponding Route Tables.
  - Did not deploy NAT Gateways or VPC Endpoints in the testing environment.

- Deployed and configured Amazon EC2:
  - Selected an Amazon Machine Image (AMI).
  - Used the `t3.micro` instance type.
  - Created and used a Key Pair.
  - Connected to the instance through SSH.
  - Verified the EC2 instance status.

- Studied Amazon EBS and its role in providing block storage for EC2 instances.

- Learned about Elastic IP and the use of public IPv4 addresses for accessing the application server.

- Understood how Amazon VPC, Subnets, Internet Gateway, Route Tables, and Security Groups work together to build the network infrastructure for the Maiora Fashion Store website.

- Completed the network infrastructure and application server preparation, providing the foundation for web environment installation and website deployment in subsequent weeks.
