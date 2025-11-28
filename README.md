Hi there 👋

- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...


Here's a comprehensive cheatsheet of all AWS services from your syllabus in table format:

| *AWS Service* | *What It Does* | *Example Scenario* |
|-----------------|------------------|----------------------|
| *IAM (Identity and Access Management)* | Manages user identities, permissions, and access controls to AWS resources through users, groups, roles, and policies | A company creates separate IAM roles for developers (read-only access) and admins (full access) to EC2 instances |
| *Amazon EC2 (Elastic Compute Cloud)* | Provides resizable virtual servers (instances) in the cloud with various instance types and pricing models | An e-commerce website runs its web application on multiple EC2 instances that scale during holiday sales |
| *Auto Scaling* | Automatically adjusts the number of EC2 instances based on demand to maintain performance and optimize costs | A video streaming service automatically adds servers during peak evening hours and removes them at night |
| *Elastic Load Balancing (ELB)* | Distributes incoming application traffic across multiple targets (EC2 instances, containers) to ensure high availability | A banking application distributes user login requests across 10 EC2 instances to prevent overload |
| *Amazon S3 (Simple Storage Service)* | Object storage service for storing and retrieving any amount of data with different storage classes for cost optimization | A media company stores millions of photos and videos, using S3 Glacier for archived content |
| *Amazon EBS (Elastic Block Store)* | Provides persistent block-level storage volumes for use with EC2 instances | A database server uses EBS volumes to store its data files that persist even if the EC2 instance is stopped |
| *Amazon Glacier* | Low-cost cloud storage service for data archiving and long-term backup with retrieval times from minutes to hours | A hospital archives patient records from 10 years ago that are rarely accessed but must be retained |
| *Amazon EFS (Elastic File System)* | Managed file storage service that can be mounted on multiple EC2 instances simultaneously | A content management system where multiple web servers need to access shared website files |
| *Amazon VPC (Virtual Private Cloud)* | Isolated virtual network where you can launch AWS resources with complete control over IP addressing, subnets, and routing | A company creates a private network with public subnet for web servers and private subnet for databases |
| *VPC Subnets* | Segments of VPC IP address range where you can place groups of isolated resources | Separating production resources in one subnet (10.0.1.0/24) and development in another (10.0.2.0/24) |
| *Route Tables* | Contains rules (routes) that determine where network traffic from your subnet or gateway is directed | Routing internet traffic from public subnet through Internet Gateway, private subnet through NAT Gateway |
| *Security Groups* | Virtual firewall that controls inbound and outbound traffic for AWS resources at the instance level | Allowing only HTTPS (port 443) traffic from the internet to web servers, blocking all other ports |
| *VPC Peering* | Networking connection between two VPCs that enables routing traffic between them using private IP addresses | Connecting a production VPC with a shared services VPC containing monitoring and logging tools |
| *AWS Direct Connect* | Dedicated private network connection from your premises to AWS, bypassing the public internet | A financial institution establishes a 10 Gbps dedicated connection for secure, low-latency data transfer |
| *Amazon CloudFront* | Content Delivery Network (CDN) that delivers data, videos, applications globally with low latency | A news website caches articles and images at edge locations worldwide for faster access |
| *Amazon RDS (Relational Database Service)* | Managed relational database service supporting multiple engines (MySQL, PostgreSQL, Oracle, SQL Server) | An online store runs its product catalog on a managed MySQL database without managing servers |
| *RDS Multi-AZ Deployments* | High availability configuration that maintains synchronous standby replica in different Availability Zone | A financial application automatically fails over to standby database if primary fails, ensuring 99.95% uptime |
| *RDS Read Replicas* | Read-only copies of database that improve read performance by distributing query load | A reporting system queries read replicas for analytics while transactional app uses primary database |
| *Amazon Aurora* | MySQL and PostgreSQL-compatible relational database with performance and availability of commercial databases | A SaaS application handles 5x more transactions than standard MySQL with Aurora's distributed architecture |
| *Amazon DynamoDB* | Fully managed NoSQL database service providing fast and predictable performance with seamless scalability | A gaming application stores player profiles and session data requiring single-digit millisecond latency |
| *DynamoDB Streams* | Captures time-ordered sequence of item-level modifications in DynamoDB tables | Triggering Lambda functions to send notifications whenever a user's profile is updated in DynamoDB |
| *AWS CloudWatch* | Monitoring and observability service that collects and tracks metrics, logs, and sets alarms | Monitoring CPU utilization of EC2 instances and sending alerts when it exceeds 80% for 5 minutes |
| *AWS CloudTrail* | Records AWS API calls and delivers log files for auditing and compliance | Security team reviews who terminated a production EC2 instance by examining CloudTrail logs |
| *AWS Config* | Tracks AWS resource configurations and changes over time for compliance and troubleshooting | Ensuring all S3 buckets have encryption enabled and receiving alerts when configuration drifts |
| *AWS Systems Manager* | Unified interface for viewing operational data and automating tasks across AWS resources | Patching 100 EC2 instances simultaneously with security updates using automated runbooks |
| *AWS Free Tier* | Allows new users to try AWS services for free within specified limits for 12 months | A startup tests EC2 t2.micro instances (750 hours/month free) before committing to paid plans |
| *AWS Billing and Account Management* | Tools to view and pay AWS bills, manage payment methods, and organize accounts | Consolidating bills from multiple departments using AWS Organizations for centralized payment |
| *AWS Budgets* | Custom budgets that alert you when costs or usage exceed (or are forecasted to exceed) budgeted amounts | Setting a $500 monthly budget and receiving email alerts when spending reaches 80% ($400) |
| *AWS Trusted Advisor* | Provides real-time guidance to optimize AWS infrastructure for cost, performance, security, and fault tolerance | Identifying underutilized EC2 instances that could be downsized to save 40% on monthly costs |
| *AWS KMS (Key Management Service)* | Managed service to create and control encryption keys used to encrypt data | Encrypting sensitive customer data in S3 using customer-managed encryption keys with automatic rotation |
| *AWS WAF (Web Application Firewall)* | Protects web applications from common web exploits like SQL injection and cross-site scripting | Blocking malicious traffic attempting SQL injection attacks on an e-commerce checkout page |
| *AWS Shield* | Managed DDoS protection service that safeguards applications running on AWS | Automatically mitigating a 50 Gbps DDoS attack targeting a public-facing website with no downtime |
| *Amazon SQS (Simple Queue Service)* | Fully managed message queuing service that enables asynchronous communication between distributed components | An order processing system where orders are queued for inventory checks before payment processing |
| *Amazon SNS (Simple Notification Service)* | Pub/sub messaging service for sending notifications to subscribers via email, SMS, HTTP, etc. | Sending SMS alerts to on-call engineers when critical production errors occur |
| *Amazon SWF (Simple Workflow Service)* | Coordinates work across distributed application components with task coordination and state management | Managing a video transcoding pipeline where encoding, thumbnails, and uploads happen in sequence |
| *AWS Step Functions* | Visual workflow service to orchestrate AWS services into serverless workflows using state machines | Coordinating a data processing pipeline: S3 upload → Lambda validation → Glue ETL → Athena query |
| *AWS Database Migration Service (DMS)* | Migrates databases to AWS with minimal downtime, supporting homogeneous and heterogeneous migrations | Migrating an on-premises Oracle database to Amazon Aurora PostgreSQL with continuous replication |
| *AWS Server Migration Service (SMS)* | Automates migration of on-premises VMware, Hyper-V, or Azure VMs to AWS | Migrating 50 VMware virtual machines to EC2 over 4 weeks with incremental replication |
| *AWS Snowball* | Petabyte-scale physical data transport device for transferring large amounts of data to/from AWS | Transferring 80TB of genomic research data to S3 using Snowball instead of 100+ days over internet |
| *AWS Snowball Edge* | Edge computing and data transfer device with onboard compute and storage capabilities | Processing IoT sensor data at an oil rig with limited connectivity before shipping device to AWS |
| *AWS Snowmobile* | Exabyte-scale data transfer service using a 45-foot shipping container truck | Migrating 100 PB data center archive to AWS Glacier using Snowmobile in a single transfer |

This cheatsheet covers all AWS services mentioned across your 8 modules with practical, real-world scenarios.
