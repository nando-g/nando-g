Hi there 👋

- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

# AWS Cloud Architecture Design - Complete Exam Cheatsheet

## 📋 Table of Contents
1. [AWS Services Overview](#aws-services-overview)
2. [Scenario-Based Problem Solving Framework](#scenario-based-problem-solving-framework)
3. [Common Architecture Patterns](#common-architecture-patterns)
4. [Service Decision Trees](#service-decision-trees)
5. [Security Best Practices](#security-best-practices)
6. [Cost Optimization](#cost-optimization)
7. [Migration Strategies](#migration-strategies)
8. [Well-Architected Framework](#well-architected-framework)
9. [S3 Storage Classes](#s3-storage-classes)
10. [High-Frequency Exam Scenarios](#high-frequency-exam-scenarios)
11. [Answer Structure Template](#answer-structure-template)

---

## AWS Services Overview

### Complete Service Reference Table

| **AWS Service** | **What It Does** | **Example Scenario** |
|-----------------|------------------|----------------------|
| **IAM (Identity and Access Management)** | Manages user identities, permissions, and access controls to AWS resources through users, groups, roles, and policies | A company creates separate IAM roles for developers (read-only access) and admins (full access) to EC2 instances |
| **Amazon EC2 (Elastic Compute Cloud)** | Provides resizable virtual servers (instances) in the cloud with various instance types and pricing models | An e-commerce website runs its web application on multiple EC2 instances that scale during holiday sales |
| **Auto Scaling** | Automatically adjusts the number of EC2 instances based on demand to maintain performance and optimize costs | A video streaming service automatically adds servers during peak evening hours and removes them at night |
| **Elastic Load Balancing (ELB)** | Distributes incoming application traffic across multiple targets (EC2 instances, containers) to ensure high availability | A banking application distributes user login requests across 10 EC2 instances to prevent overload |
| **Amazon S3 (Simple Storage Service)** | Object storage service for storing and retrieving any amount of data with different storage classes for cost optimization | A media company stores millions of photos and videos, using S3 Glacier for archived content |
| **Amazon EBS (Elastic Block Store)** | Provides persistent block-level storage volumes for use with EC2 instances | A database server uses EBS volumes to store its data files that persist even if the EC2 instance is stopped |
| **Amazon Glacier** | Low-cost cloud storage service for data archiving and long-term backup with retrieval times from minutes to hours | A hospital archives patient records from 10 years ago that are rarely accessed but must be retained |
| **Amazon EFS (Elastic File System)** | Managed file storage service that can be mounted on multiple EC2 instances simultaneously | A content management system where multiple web servers need to access shared website files |
| **Amazon VPC (Virtual Private Cloud)** | Isolated virtual network where you can launch AWS resources with complete control over IP addressing, subnets, and routing | A company creates a private network with public subnet for web servers and private subnet for databases |
| **VPC Subnets** | Segments of VPC IP address range where you can place groups of isolated resources | Separating production resources in one subnet (10.0.1.0/24) and development in another (10.0.2.0/24) |
| **Route Tables** | Contains rules (routes) that determine where network traffic from your subnet or gateway is directed | Routing internet traffic from public subnet through Internet Gateway, private subnet through NAT Gateway |
| **Security Groups** | Virtual firewall that controls inbound and outbound traffic for AWS resources at the instance level | Allowing only HTTPS (port 443) traffic from the internet to web servers, blocking all other ports |
| **VPC Peering** | Networking connection between two VPCs that enables routing traffic between them using private IP addresses | Connecting a production VPC with a shared services VPC containing monitoring and logging tools |
| **AWS Direct Connect** | Dedicated private network connection from your premises to AWS, bypassing the public internet | A financial institution establishes a 10 Gbps dedicated connection for secure, low-latency data transfer |
| **Amazon CloudFront** | Content Delivery Network (CDN) that delivers data, videos, applications globally with low latency | A news website caches articles and images at edge locations worldwide for faster access |
| **Amazon RDS (Relational Database Service)** | Managed relational database service supporting multiple engines (MySQL, PostgreSQL, Oracle, SQL Server) | An online store runs its product catalog on a managed MySQL database without managing servers |
| **RDS Multi-AZ Deployments** | High availability configuration that maintains synchronous standby replica in different Availability Zone | A financial application automatically fails over to standby database if primary fails, ensuring 99.95% uptime |
| **RDS Read Replicas** | Read-only copies of database that improve read performance by distributing query load | A reporting system queries read replicas for analytics while transactional app uses primary database |
| **Amazon Aurora** | MySQL and PostgreSQL-compatible relational database with performance and availability of commercial databases | A SaaS application handles 5x more transactions than standard MySQL with Aurora's distributed architecture |
| **Amazon DynamoDB** | Fully managed NoSQL database service providing fast and predictable performance with seamless scalability | A gaming application stores player profiles and session data requiring single-digit millisecond latency |
| **DynamoDB Streams** | Captures time-ordered sequence of item-level modifications in DynamoDB tables | Triggering Lambda functions to send notifications whenever a user's profile is updated in DynamoDB |
| **AWS CloudWatch** | Monitoring and observability service that collects and tracks metrics, logs, and sets alarms | Monitoring CPU utilization of EC2 instances and sending alerts when it exceeds 80% for 5 minutes |
| **AWS CloudTrail** | Records AWS API calls and delivers log files for auditing and compliance | Security team reviews who terminated a production EC2 instance by examining CloudTrail logs |
| **AWS Config** | Tracks AWS resource configurations and changes over time for compliance and troubleshooting | Ensuring all S3 buckets have encryption enabled and receiving alerts when configuration drifts |
| **AWS Systems Manager** | Unified interface for viewing operational data and automating tasks across AWS resources | Patching 100 EC2 instances simultaneously with security updates using automated runbooks |
| **AWS Free Tier** | Allows new users to try AWS services for free within specified limits for 12 months | A startup tests EC2 t2.micro instances (750 hours/month free) before committing to paid plans |
| **AWS Billing and Account Management** | Tools to view and pay AWS bills, manage payment methods, and organize accounts | Consolidating bills from multiple departments using AWS Organizations for centralized payment |
| **AWS Budgets** | Custom budgets that alert you when costs or usage exceed (or are forecasted to exceed) budgeted amounts | Setting a $500 monthly budget and receiving email alerts when spending reaches 80% ($400) |
| **AWS Trusted Advisor** | Provides real-time guidance to optimize AWS infrastructure for cost, performance, security, and fault tolerance | Identifying underutilized EC2 instances that could be downsized to save 40% on monthly costs |
| **AWS KMS (Key Management Service)** | Managed service to create and control encryption keys used to encrypt data | Encrypting sensitive customer data in S3 using customer-managed encryption keys with automatic rotation |
| **AWS WAF (Web Application Firewall)** | Protects web applications from common web exploits like SQL injection and cross-site scripting | Blocking malicious traffic attempting SQL injection attacks on an e-commerce checkout page |
| **AWS Shield** | Managed DDoS protection service that safeguards applications running on AWS | Automatically mitigating a 50 Gbps DDoS attack targeting a public-facing website with no downtime |
| **Amazon SQS (Simple Queue Service)** | Fully managed message queuing service that enables asynchronous communication between distributed components | An order processing system where orders are queued for inventory checks before payment processing |
| **Amazon SNS (Simple Notification Service)** | Pub/sub messaging service for sending notifications to subscribers via email, SMS, HTTP, etc. | Sending SMS alerts to on-call engineers when critical production errors occur |
| **Amazon SWF (Simple Workflow Service)** | Coordinates work across distributed application components with task coordination and state management | Managing a video transcoding pipeline where encoding, thumbnails, and uploads happen in sequence |
| **AWS Step Functions** | Visual workflow service to orchestrate AWS services into serverless workflows using state machines | Coordinating a data processing pipeline: S3 upload → Lambda validation → Glue ETL → Athena query |
| **AWS Database Migration Service (DMS)** | Migrates databases to AWS with minimal downtime, supporting homogeneous and heterogeneous migrations | Migrating an on-premises Oracle database to Amazon Aurora PostgreSQL with continuous replication |
| **AWS Server Migration Service (SMS)** | Automates migration of on-premises VMware, Hyper-V, or Azure VMs to AWS | Migrating 50 VMware virtual machines to EC2 over 4 weeks with incremental replication |
| **AWS Snowball** | Petabyte-scale physical data transport device for transferring large amounts of data to/from AWS | Transferring 80TB of genomic research data to S3 using Snowball instead of 100+ days over internet |
| **AWS Snowball Edge** | Edge computing and data transfer device with onboard compute and storage capabilities | Processing IoT sensor data at an oil rig with limited connectivity before shipping device to AWS |
| **AWS Snowmobile** | Exabyte-scale data transfer service using a 45-foot shipping container truck | Migrating 100 PB data center archive to AWS Glacier using Snowmobile in a single transfer |

---

## Scenario-Based Problem Solving Framework

### What Examiners Want to See:
✅ Clear understanding of requirements  
✅ Appropriate AWS service selection  
✅ Strong justification for choices  
✅ Security considerations  
✅ Cost optimization awareness  
✅ High availability thinking  
✅ Best practices application

### Question Pattern Analysis:
✅ 100% case-based scenarios - No theory-only questions  
✅ Multi-service integration - Questions involve 3-5 AWS services  
✅ Architecture design - Diagrams often required/helpful  
✅ Real-world companies - Scenarios based on actual use cases  
✅ Best practices - Security, cost, and performance always considered

### Common Question Structures:
1. Company scenario → Requirements → Design architecture
2. Existing setup → Problems → Optimization solution
3. Migration need → Constraints → Migration strategy
4. Security incident → Investigation → Remediation

### Step 1: Identify the Core Requirement

| **Keyword in Question** | **Primary Need** | **Go-To Services** |
|------------------------|------------------|-------------------|
| "highly available" | 99.99% uptime | Multi-AZ, ELB, Auto Scaling, Route 53 |
| "cost optimization" | Reduce spending | Reserved Instances, S3 lifecycle, Spot instances |
| "scalable" | Handle variable load | Auto Scaling, CloudFront, DynamoDB |
| "secure" | Protect data/access | IAM, KMS, Security Groups, WAF, Shield |
| "fast global access" | Low latency worldwide | CloudFront, Route 53, Global Accelerator |
| "migration" | Move to AWS | DMS, SMS, Snowball, Application Discovery |
| "serverless" | No server management | Lambda, DynamoDB, S3, API Gateway |
| "disaster recovery" | Business continuity | Multi-region, S3 cross-region replication, RDS backup |

---

## Common Architecture Patterns

### Pattern 1: 3-Tier Web Application (Most Common!)

**Scenario**: E-commerce website needs high availability and scalability

**Architecture**:
```
Users → Route 53 → CloudFront → 
  → Application Load Balancer → 
  → Auto Scaling Group (EC2 in Multi-AZ) → 
  → RDS Multi-AZ (Primary + Standby) → 
  → S3 (product images) + ElastiCache (session data)
```

**Services Used**: 
- Route 53 (DNS)
- CloudFront (CDN)
- ALB (Load Balancing)
- Auto Scaling (Elasticity)
- EC2 (Compute)
- RDS Multi-AZ (Database HA)
- S3 (Object Storage)
- ElastiCache (Caching)

**Security**: 
- Security Groups
- HTTPS/TLS
- IAM roles
- KMS encryption

**Monitoring**: 
- CloudWatch
- CloudTrail
- Config

---

### Pattern 2: Disaster Recovery / High Availability

**Scenario**: Financial company needs 99.99% availability with minimal data loss

| **Component** | **Solution** | **Why** |
|--------------|-------------|---------|
| **Compute** | Auto Scaling Group across 3 AZs | Survives AZ failure |
| **Database** | RDS Multi-AZ + Read Replicas | Automatic failover + read scaling |
| **Storage** | S3 with Cross-Region Replication | 99.999999999% durability |
| **Load Balancing** | Application Load Balancer | Health checks + auto-rerouting |
| **Backup** | RDS automated backups + S3 versioning | Point-in-time recovery |

**DR Strategy**: Pilot Light or Warm Standby in another region

**RPO (Recovery Point Objective)**: < 1 minute (Multi-AZ synchronous replication)  
**RTO (Recovery Time Objective)**: < 5 minutes (automatic failover)

---

### Pattern 3: Cost Optimization

**Scenario**: Startup needs to reduce AWS bill by 40%

| **Current Problem** | **Solution** | **Savings** |
|-------------------|------------|-----------|
| On-Demand EC2 24/7 | Reserved Instances (1-3 year) | Up to 72% |
| Always-running development | Auto Scaling with scheduled policies | 50% in non-business hours |
| S3 all Standard storage | Lifecycle policy → Infrequent Access → Glacier | 70% on archived data |
| Oversized instances | Right-sizing with CloudWatch metrics | 30-40% |
| No monitoring | AWS Budgets + Trusted Advisor | Prevent overspending |
| Multiple NAT Gateways | Single NAT Gateway per AZ | Consolidation savings |

**Tools to Use**: 
- Cost Explorer
- Trusted Advisor
- AWS Budgets
- Compute Optimizer

---

### Pattern 4: Security Incident Response

**Scenario**: Unauthorized access detected in production environment

**Investigation Steps**:
1. **Check CloudTrail** → Who made the API calls?
2. **Review IAM policies** → What permissions were used?
3. **Analyze VPC Flow Logs** → What network traffic occurred?
4. **Check Security Groups** → Were rules modified?
5. **Review Config** → What resources changed?

**Remediation**:
- Rotate compromised credentials immediately
- Enable MFA on all accounts
- Implement least privilege IAM policies
- Enable GuardDuty for threat detection
- Set up CloudWatch alarms for suspicious activity
- Enable AWS WAF for application protection

---

## Service Decision Trees

### Storage Decision

```
Need storage?
├─ Object storage (files, backups, media)
│  ├─ Frequent access → S3 Standard
│  ├─ Infrequent access → S3 IA / One Zone-IA
│  └─ Archive (rarely accessed) → S3 Glacier / Deep Archive
├─ Block storage (databases, boot volumes)
│  ├─ High performance → EBS Provisioned IOPS
│  └─ General purpose → EBS GP3
└─ File storage (shared across instances)
   └─ Multiple EC2 need same files → EFS
```

### Database Decision

```
Need database?
├─ Relational (SQL, structured data)
│  ├─ Need MySQL/PostgreSQL → Aurora (best performance)
│  ├─ Specific engine needed → RDS (MySQL, PostgreSQL, Oracle, SQL Server)
│  └─ High availability → Enable Multi-AZ
├─ NoSQL (flexible schema, high scale)
│  ├─ Key-value, millisecond latency → DynamoDB
│  └─ In-memory caching → ElastiCache (Redis/Memcached)
└─ Data warehouse (analytics)
   └─ Petabyte-scale analytics → Redshift
```

### Compute Decision

```
Need compute?
├─ Full control needed → EC2
│  ├─ Variable workload → Auto Scaling + Spot Instances
│  ├─ Steady workload → Reserved Instances
│  └─ Temporary workload → On-Demand
├─ Containerized apps → ECS / EKS
├─ No server management → Lambda (serverless)
└─ Batch processing → AWS Batch
```

---

## Security Best Practices

### Security Layers (Always Mention These!)

| **Layer** | **Best Practice** | **AWS Service** |
|-----------|------------------|----------------|
| **Identity** | Least privilege access, MFA enabled | IAM policies, MFA |
| **Network** | Private subnets for databases, NACLs + Security Groups | VPC, Security Groups |
| **Data in Transit** | HTTPS/TLS encryption everywhere | ACM, CloudFront |
| **Data at Rest** | Encrypt all storage | KMS, S3 encryption, EBS encryption |
| **Application** | Protect from common attacks | WAF, Shield (DDoS) |
| **Monitoring** | Log everything, detect threats | CloudTrail, GuardDuty, Config |
| **Compliance** | Audit configurations | AWS Config, AWS Artifact |

**Golden Rule**: Never hardcode credentials! Use IAM roles for EC2/Lambda

### IAM Best Practices
- Enable MFA for root account and privileged users
- Use IAM roles instead of access keys
- Implement least privilege principle
- Rotate credentials regularly
- Use IAM policies to enforce MFA
- Enable CloudTrail for API logging

### Network Security
- Use Security Groups (stateful) for instance-level firewall
- Use NACLs (stateless) for subnet-level firewall
- Keep databases in private subnets
- Use VPC Flow Logs for network monitoring
- Implement VPN or Direct Connect for hybrid connectivity

### Data Protection
- Enable encryption at rest (S3, EBS, RDS)
- Enable encryption in transit (TLS/SSL)
- Use KMS for key management
- Enable S3 versioning for accidental deletion protection
- Implement S3 bucket policies and ACLs

---

## Cost Optimization

### Cost Optimization Checklist

✅ **Right-sizing**: Use CloudWatch to identify underutilized resources  
✅ **Reserved Instances**: For predictable workloads (1-3 year commitment)  
✅ **Spot Instances**: For fault-tolerant workloads (up to 90% discount)  
✅ **S3 Lifecycle**: Automatically move old data to cheaper storage  
✅ **Auto Scaling**: Scale down during off-peak hours  
✅ **Delete unused resources**: Unattached EBS volumes, old snapshots  
✅ **Use AWS Budgets**: Set alerts at 80% of budget  
✅ **Leverage Trusted Advisor**: Free cost optimization recommendations

### EC2 Pricing Models

| **Model** | **Use Case** | **Savings** | **Commitment** |
|-----------|-------------|------------|---------------|
| **On-Demand** | Unpredictable, short-term workloads | 0% (baseline) | None |
| **Reserved (1-year)** | Steady-state, predictable usage | 40% | 1 year |
| **Reserved (3-year)** | Long-term, stable workloads | 72% | 3 years |
| **Spot Instances** | Fault-tolerant, flexible timing | Up to 90% | None (can be terminated) |
| **Savings Plans** | Flexible compute usage | Up to 72% | 1 or 3 years |

### Cost Monitoring Tools

1. **AWS Cost Explorer**: Visualize and analyze costs
2. **AWS Budgets**: Set custom cost/usage budgets with alerts
3. **AWS Trusted Advisor**: Cost optimization recommendations
4. **AWS Compute Optimizer**: Right-sizing recommendations
5. **AWS Cost and Usage Reports**: Detailed billing data

---

## Migration Strategies

### The 6 R's of Migration

| **Strategy** | **When to Use** | **Example** | **Effort** |
|-------------|----------------|------------|-----------|
| **Rehost** (Lift & Shift) | Quick migration, minimal changes | SMS to move VMs → EC2 | Low |
| **Replatform** | Minor optimizations | Move database to RDS instead of EC2 | Medium |
| **Repurchase** | Replace with SaaS | Move email to AWS WorkMail | Low |
| **Refactor** | Modernize to cloud-native | Rebuild app with Lambda + DynamoDB | High |
| **Retire** | Decommission unnecessary systems | Shut down unused applications | Low |
| **Retain** | Keep on-premises for now | Mainframe systems not ready to migrate | None |

### Data Migration Tools

**Decision Matrix**:

| **Data Size** | **Time Constraint** | **Recommended Tool** |
|--------------|-------------------|---------------------|
| < 10 TB | Network available | AWS DataSync, Direct Connect |
| 10-80 TB | Faster than network | AWS Snowball |
| 80 TB - 100 PB | Massive transfer | AWS Snowball Edge |
| > 100 PB | Data center migration | AWS Snowmobile |

### Database Migration

**AWS Database Migration Service (DMS)**:
- **Homogeneous**: Oracle → Oracle, MySQL → MySQL
- **Heterogeneous**: Oracle → Aurora PostgreSQL, SQL Server → MySQL

**Steps**:
1. Create replication instance
2. Define source and target endpoints
3. Create migration task
4. Start replication (full load + CDC)
5. Switch over when synchronized

---

## Well-Architected Framework

### The 5 Pillars

#### 1. Operational Excellence
**Design Principles**:
- Perform operations as code (Infrastructure as Code)
- Make frequent, small, reversible changes
- Refine operations procedures frequently
- Anticipate failure
- Learn from operational failures

**Key Services**:
- CloudFormation (IaC)
- Systems Manager
- CloudWatch
- AWS X-Ray

#### 2. Security
**Design Principles**:
- Implement strong identity foundation (IAM)
- Enable traceability (CloudTrail)
- Apply security at all layers
- Automate security best practices
- Protect data in transit and at rest
- Keep people away from data
- Prepare for security events

**Key Services**:
- IAM, MFA
- CloudTrail, Config
- KMS
- Security Groups, NACLs
- WAF, Shield
- GuardDuty

#### 3. Reliability
**Design Principles**:
- Automatically recover from failure
- Test recovery procedures
- Scale horizontally
- Stop guessing capacity
- Manage change through automation

**Key Services**:
- Multi-AZ deployments
- Auto Scaling
- Route 53
- RDS Multi-AZ
- S3 (11 9's durability)
- CloudWatch

#### 4. Performance Efficiency
**Design Principles**:
- Democratize advanced technologies
- Go global in minutes
- Use serverless architectures
- Experiment more often
- Consider mechanical sympathy

**Key Services**:
- Auto Scaling
- Lambda
- EBS, S3
- RDS, DynamoDB
- CloudFront

#### 5. Cost Optimization
**Design Principles**:
- Implement cloud financial management
- Adopt consumption model
- Measure overall efficiency
- Stop spending on undifferentiated heavy lifting
- Analyze and attribute expenditure

**Key Services**:
- Cost Explorer
- AWS Budgets
- Trusted Advisor
- Reserved Instances
- Auto Scaling

---

## S3 Storage Classes

### Complete S3 Storage Classes Overview

| **Storage Class** | **Use Case** | **Availability** | **Durability** | **Cost** | **Retrieval Time** |
|------------------|-------------|-----------------|---------------|----------|-------------------|
| **S3 Standard** | Frequently accessed data | 99.99% | 11 9's | $$$$$ | Milliseconds |
| **S3 Intelligent-Tiering** | Unknown/changing access patterns | 99.9% | 11 9's | $$$$ + monitoring fee | Milliseconds |
| **S3 Standard-IA** | Infrequently accessed data | 99.9% | 11 9's | $$$ + retrieval fee | Milliseconds |
| **S3 One Zone-IA** | Infrequent access, recreatable data | 99.5% | 11 9's (1 AZ) | $$ + retrieval fee | Milliseconds |
| **S3 Glacier Instant Retrieval** | Archive with instant access | 99.9% | 11 9's | $$ + retrieval fee | Milliseconds |
| **S3 Glacier Flexible Retrieval** | Archive with flexible retrieval | 99.99% | 11 9's | $ + retrieval fee | Minutes to hours |
| **S3 Glacier Deep Archive** | Long-term archive (7-10 years) | 99.99% | 11 9's | $ (lowest) + retrieval fee | 12-48 hours |

**Note**: 11 9's = 99.999999999% durability

### Detailed S3 Storage Classes

#### 1. S3 Standard 💎
**Purpose**: General-purpose storage for frequently accessed data

**Characteristics**:
- Low latency, high throughput
- Stored across ≥3 Availability Zones
- Most expensive storage cost
- No retrieval fees
- No minimum storage duration

**Perfect For**:
- Active website content
- Mobile/gaming applications
- Big data analytics
- Content distribution

**Pricing**: ~$0.023 per GB/month

---

#### 2. S3 Intelligent-Tiering 🤖
**Purpose**: Automatic cost optimization for data with unknown access patterns

**How It Works**:
- Monitors access patterns automatically
- Moves objects between tiers based on usage:
  - **Frequent Access tier** (accessed in last 30 days)
  - **Infrequent Access tier** (30-90 days)
  - **Archive Instant Access** (90-180 days)
  - **Archive Access** (optional, 180-730 days)
  - **Deep Archive Access** (optional, >730 days)

**Characteristics**:
- Small monthly monitoring fee (~$0.0025 per 1,000 objects)
- No retrieval fees
- Automatic savings without performance impact

**Perfect For**:
- Data lakes
- Unpredictable workloads
- User-generated content

**Pricing**: ~$0.023 per GB/month + monitoring fee

---

#### 3. S3 Standard-IA (Infrequent Access) 📊
**Purpose**: Data accessed less frequently but needs rapid access when required

**Characteristics**:
- Lower storage cost than Standard
- Retrieval fee per GB accessed
- Minimum storage duration: 30 days
- Minimum object size: 128 KB
- Stored across ≥3 AZs

**Perfect For**:
- Backups
- Disaster recovery files
- Long-term storage with occasional access

**Pricing**: ~$0.0125 per GB/month + $0.01 per GB retrieved

---

#### 4. S3 One Zone-IA 🎯
**Purpose**: Infrequently accessed, recreatable data that doesn't need multi-AZ resilience

**Characteristics**:
- 20% cheaper than Standard-IA
- Stored in single AZ (higher risk)
- Same retrieval fees as Standard-IA
- Minimum storage: 30 days

**Perfect For**:
- Secondary backup copies
- Easily reproducible data
- Thumbnails, resized images

**Pricing**: ~$0.01 per GB/month + retrieval fees

**⚠️ Warning**: If the AZ is destroyed, data is lost

---

#### 5. S3 Glacier Instant Retrieval ❄️⚡
**Purpose**: Archive data that needs instant access (milliseconds) but accessed quarterly

**Characteristics**:
- Lowest cost for instant access archive
- Millisecond retrieval (same as Standard)
- Minimum storage: 90 days
- Higher retrieval costs

**Perfect For**:
- Medical images (need instant access for emergencies)
- Quarterly reports
- Archived news footage

**Pricing**: ~$0.004 per GB/month + $0.03 per GB retrieved

---

#### 6. S3 Glacier Flexible Retrieval 🧊
(Formerly S3 Glacier)

**Purpose**: Archive data with flexible retrieval times (minutes to hours)

**Retrieval Options**:
| **Speed** | **Time** | **Cost** |
|-----------|----------|----------|
| Expedited | 1-5 minutes | $$$$ |
| Standard | 3-5 hours | $$ |
| Bulk | 5-12 hours | $ (free for first 10 GB) |

**Characteristics**:
- Very low storage cost
- Minimum storage: 90 days
- Retrieval fees apply

**Perfect For**:
- Long-term backups
- Digital preservation
- Compliance archives (7-year retention)

**Pricing**: ~$0.0036 per GB/month + retrieval fees

---

#### 7. S3 Glacier Deep Archive 🏔️
**Purpose**: Lowest-cost storage for long-term data retention (7-10+ years)

**Retrieval Options**:
| **Speed** | **Time** | **Cost** |
|-----------|----------|----------|
| Standard | 12 hours | $$ |
| Bulk | 48 hours | $ |

**Characteristics**:
- Cheapest storage class
- Minimum storage: 180 days
- Replicated across ≥3 AZs
- Designed for data accessed <1 time/year

**Perfect For**:
- Regulatory archives (financial, healthcare)
- Digital tape replacement
- Long-term datasets

**Pricing**: ~$0.00099 per GB/month (~$1 per TB!)

---

### S3 Lifecycle Policies (Automation)

**Example Lifecycle Policy**:

```
Day 0-30:     S3 Standard (frequent access)
Day 30-90:    S3 Standard-IA (less frequent)
Day 90-365:   S3 Glacier Flexible Retrieval (archive)
Day 365+:     S3 Glacier Deep Archive (long-term)
Delete:       After 2,555 days (7 years)
```

**Use Case**: Log files
- **Day 0-30**: Active analysis → Standard
- **Day 30-90**: Occasional queries → Standard-IA
- **Day 90-365**: Compliance checks → Glacier Flexible
- **Day 365+**: Legal retention → Glacier Deep Archive
- **After 7 years**: Delete automatically

---

### S3 Decision Tree

```
Need S3 storage?
│
├─ Accessed frequently (daily/weekly)?
│  └─ YES → S3 Standard
│
├─ Access pattern unknown/changing?
│  └─ YES → S3 Intelligent-Tiering
│
├─ Accessed monthly (infrequent)?
│  ├─ Need multi-AZ resilience?
│  │  ├─ YES → S3 Standard-IA
│  │  └─ NO (recreatable data) → S3 One Zone-IA
│
├─ Accessed quarterly (need instant access)?
│  └─ YES → S3 Glacier Instant Retrieval
│
├─ Accessed 1-2 times/year (can wait hours)?
│  └─ YES → S3 Glacier Flexible Retrieval
│
└─ Long-term archive (7+ years, rarely accessed)?
   └─ YES → S3 Glacier Deep Archive
```

---

### Cost Comparison Example

**Scenario**: Store 1 TB (1,024 GB) for 1 year

| **Storage Class** | **Monthly Cost** | **Annual Cost** |
|------------------|-----------------|---------------|
| S3 Standard | $23.55 | $282.60 |
| S3 Intelligent-Tiering | $23.55 + monitoring | ~$290 |
| S3 Standard-IA | $12.80 | $153.60 |
| S3 One Zone-IA | $10.24 | $122.88 |
| S3 Glacier Instant Retrieval | $4.10 | $49.20 |
| S3 Glacier Flexible | $3.69 | $44.28 |
| S3 Glacier Deep Archive | $1.01 | **$12.14** ⭐ |

**Savings**: Deep Archive saves **$270.46** (96%) vs Standard!

---

## High-Frequency Exam Scenarios

### Scenario 1: E-commerce Peak Season
**Problem**: Website crashes during Black Friday sales

**Solution**:
- **CloudFront**: Cache static content globally
- **Auto Scaling**: Automatically add EC2 instances during peak
- **ElastiCache**: Cache database queries (session data)
- **DynamoDB**: Serverless, auto-scaling database for product catalog
- **RDS Read Replicas**: Offload read traffic from primary database

**Architecture**:
```
CloudFront → ALB → Auto Scaling Group → 
  → ElastiCache (Redis) → RDS Multi-AZ + Read Replicas
  → S3 (product images)
```

---

### Scenario 2: Compliance & Audit
**Problem**: Need to track all API calls for SOC 2 compliance

**Solution**:
- **CloudTrail**: Enable in all regions, log to S3
- **AWS Config**: Track resource configuration changes
- **S3 Bucket**: Store logs with encryption (KMS)
- **S3 Lifecycle**: Move old logs to Glacier after 90 days
- **CloudWatch Logs**: Real-time monitoring and alerting
- **Athena**: Query CloudTrail logs using SQL

**Compliance Requirements**:
- Log retention: 7 years
- Encryption: KMS-managed keys
- Access control: S3 bucket policies, IAM
- Monitoring: CloudWatch alarms for suspicious activity

---

### Scenario 3: Database Performance
**Problem**: Reporting queries slow down transactional database

**Solution**:
- **RDS Read Replicas**: Create 2-3 read replicas for reporting
- **Route traffic**: Production app → Primary DB, Reports → Read Replicas
- **ElastiCache**: Cache frequent queries
- **DynamoDB**: Consider migrating to NoSQL if schema allows

**Benefits**:
- Transactional workload unaffected
- Reporting queries don't impact production
- Can have replicas in different regions for global reporting

---

### Scenario 4: Global Application
**Problem**: Users in Asia experience high latency (500ms+)

**Solution**:
- **CloudFront**: CDN with edge locations in Asia
- **Route 53**: Latency-based routing to nearest region
- **Multi-Region Deployment**: Deploy in us-east-1, ap-southeast-1, eu-west-1
- **S3 Cross-Region Replication**: Replicate static assets
- **DynamoDB Global Tables**: Multi-region database replication

**Result**: Latency reduced from 500ms to 50ms

---

### Scenario 5: Hybrid Cloud
**Problem**: Need secure connection between on-premises and AWS

**Options**:

| **Solution** | **Use Case** | **Speed** | **Cost** |
|-------------|-------------|-----------|----------|
| **VPN** | Low-moderate bandwidth, encrypted | Up to 1.25 Gbps | $ |
| **Direct Connect** | High bandwidth, predictable latency | 1-100 Gbps | $$$ |
| **Direct Connect + VPN** | High bandwidth + encryption | 1-100 Gbps | $$$$ |

**Recommendation**: 
- **VPN**: For development/testing environments
- **Direct Connect**: For production, sensitive data transfer

---

### Scenario 6: Development Environment Cost
**Problem**: Dev environment costs too much (running 24/7)

**Solution**:
- **Auto Scaling Scheduled Actions**: 
  - Scale to 0 instances at 7 PM
  - Scale to required capacity at 8 AM
- **Lambda**: Replace always-on services with event-driven functions
- **RDS**: Stop instances during non-business hours
- **Tags**: Tag dev resources for easy identification
- **AWS Budgets**: Alert when dev spending exceeds $X

**Savings**: 50-60% reduction in dev environment costs

---

## Answer Structure Template

### For Architecture Design Questions

#### 1. Understand Requirements (2 marks)
State the key requirements clearly:
- **Availability**: 99.99% uptime required
- **Scalability**: Handle 10x traffic during peak
- **Security**: PCI-DSS compliance for payment data
- **Cost**: Optimize for $5,000/month budget

#### 2. Design Architecture (6 marks)

**Frontend Layer**:
- CloudFront + S3 for static content (HTML, CSS, images)
- WAF for application protection

**Application Layer**:
- Application Load Balancer distributing traffic
- Auto Scaling Group (3-10 EC2 instances) across 3 AZs
- ElastiCache (Redis) for session management

**Database Layer**:
- RDS Multi-AZ (PostgreSQL) for transactional data
- Read Replicas (2) for reporting queries
- DynamoDB for user activity tracking

**Storage Layer**:
- S3 Standard for active uploads
- S3 Lifecycle policy to Glacier after 90 days

**Monitoring & Security**:
- CloudWatch for metrics and alarms
- CloudTrail for API auditing
- AWS Config for compliance
- KMS for encryption key management

#### 3. Justify Choices (4 marks)

**Why CloudFront?**
- Reduces latency for global users
- Offloads traffic from origin servers
- DDoS protection with Shield

**Why Multi-AZ RDS?**
- Automatic failover in <2 minutes
- Synchronous replication ensures no data loss
- Meets 99.99% availability requirement

**Why Auto Scaling?**
- Handles variable traffic (10x peak capacity)
- Scales down during off-peak to save costs
- Health checks replace unhealthy instances

**Why KMS?**
- Centralized encryption key management
- Automatic key rotation
- Meets PCI-DSS compliance requirements

#### 4. Best Practices (3 marks)

**Security**:
- Least privilege IAM policies for all services
- All data encrypted at rest (S3, EBS, RDS) using KMS
- Security Groups: Only allow necessary ports
- Private subnets for database layer

**Cost Optimization**:
- Reserved Instances for baseline capacity (40% savings)
- Spot Instances for batch processing (90% savings)
- S3 Lifecycle policies for old data
- CloudWatch alerts at 80% of budget

**Monitoring & Operations**:
- CloudWatch alarms for CPU > 80%, Disk > 85%
- SNS notifications to operations team
- Automated backups (RDS daily, S3 versioning)
- Regular disaster recovery testing

---

## Quick Reference: Service Combinations

| **Use Case** | **Services to Combine** |
|-------------|------------------------|
| Highly Available Web App | Route 53 + CloudFront + ALB + Auto Scaling + RDS Multi-AZ |
| Secure Storage | S3 + KMS + Bucket Policies + Versioning + Lifecycle |
| Serverless API | API Gateway + Lambda + DynamoDB + Cognito |
| Video Streaming | CloudFront + S3 + MediaConvert + ElastiCache |
| Big Data Processing | S3 + EMR + Redshift + Athena + QuickSight |
| Microservices | ECS/EKS + ALB + RDS/DynamoDB + CloudWatch |
| Disaster Recovery | Multi-region RDS + S3 CRR + Route 53 failover + Lambda |
| Monitoring & Compliance | CloudWatch + CloudTrail + Config + GuardDuty + Security Hub |
| Database Migration | DMS + Schema Conversion Tool + Snowball (large data) |
| Hybrid Architecture | Direct Connect/VPN + Storage Gateway + Route 53 |

---

## Golden Rules for Exam Success

### ✅ Critical Rules (Never Forget!)

1. **Always think Multi-AZ** for high availability
2. **Always encrypt** sensitive data (at rest & in transit)
3. **Always use IAM roles** (never hardcode credentials)
4. **Always mention monitoring** (CloudWatch, CloudTrail)
5. **Always consider cost** (Reserved Instances, lifecycle policies)
6. **Always justify your choices** with business requirements
7. **Draw diagrams** when possible (visual = more marks)
8. **Security in layers** (defense in depth)
9. **Automate everything** (IaC, Auto Scaling, backups)
10. **Test disaster recovery** regularly

### 🎯 Exam Day Checklist

**Before Starting**:
- Read question twice, underline keywords
- Identify: availability, scalability, security, cost requirements
- Sketch architecture mentally before writing

**While Answering**:
- Start with high-level architecture
- Explain each service choice
- Mention security at every layer
- Include monitoring and backup strategies
- Show cost optimization awareness

**Before Submitting**:
- Check all requirements addressed
- Verify service names are correct
- Ensure justifications are clear
- Add diagram if helpful

---

## Module-Wise Important Topics

### Module 1: IAM (3 hours)
**High Priority**:
- IAM Policies (JSON structure)
- IAM Roles vs Users
- Cross-account access
- MFA enforcement

### Module 2: Compute & Storage (6 hours)
**High Priority**:
- EC2 instance types and use cases
- Auto Scaling policies (target tracking, step scaling)
- EBS types (gp3, io2, st1, sc1)
- S3 storage classes and lifecycle

### Module 3: Networking (6 hours)
**High Priority**:
- VPC design (CIDR, subnets)
- Security Groups vs NACLs
- NAT Gateway vs Internet Gateway
- VPC Peering scenarios

### Module 4: Databases (6 hours)
**High Priority**:
- RDS Multi-AZ vs Read Replicas
- Aurora features and benefits
- DynamoDB vs RDS decision
- Database migration strategies

### Module 5: Management Tools (4 hours)
**High Priority**:
- CloudWatch metrics and alarms
- CloudTrail for auditing
- Cost optimization with Budgets and Trusted Advisor

### Module 6: Security (4 hours)
**High Priority**:
- KMS encryption (at rest)
- WAF rules and conditions
- Security incident response
- Shared Responsibility Model

### Module 7: Application Integration (8 hours)
**High Priority**:
- SQS vs SNS vs EventBridge
- Well-Architected Framework pillars
- Architectural patterns (3-tier, serverless, microservices)

### Module 8: Migration (8 hours)
**High Priority**:
- 6 R's migration strategies
- DMS for database migration
- Snowball family decision matrix
- Hybrid architecture patterns

---

## Common Mistakes to Avoid

❌ **Don't**: Choose services without justification  
✅ **Do**: Explain WHY each service is appropriate

❌ **Don't**: Ignore security in your architecture  
✅ **Do**: Mention encryption, IAM, Security Groups

❌ **Don't**: Forget about cost optimization  
✅ **Do**: Suggest Reserved Instances, S3 lifecycle, right-sizing

❌ **Don't**: Design single-AZ solutions for HA requirements  
✅ **Do**: Always use Multi-AZ for high availability

❌ **Don't**: Use generic answers for every scenario  
✅ **Do**: Customize solution based on specific requirements

❌ **Don't**: Overlook monitoring and backup strategies  
✅ **Do**: Include CloudWatch, CloudTrail, automated backups

❌ **Don't**: Design without considering scalability  
✅ **Do**: Use Auto Scaling, DynamoDB, Lambda for elasticity

---

## Final Tips

### Time Management
- **5 mark question**: 7-8 minutes
- **10 mark question**: 15-18 minutes
- **15 mark question**: 22-25 minutes

### Writing Strategy
1. **Introduction** (10%): State requirements and approach
2. **Architecture** (50%): Detailed design with services
3. **Justification** (30%): Why each choice makes sense
4. **Best Practices** (10%): Security, cost, monitoring

### Bonus Marks
- Clean, labeled diagrams (+1-2 marks)
- Real-world service names (not generic "database")
- Specific configurations (t3.medium, gp3, Multi-AZ)
- Cost estimates or comparisons
- Alternative solutions with trade-offs

---

## Good luck with your Cloud Architecture Design exam! 🚀

**Remember**: AWS is about building reliable, secure, scalable, and cost-effective solutions. Always think from a business perspective, not just technical implementation.

**Key to Success**: 
- Understand the WHY behind each service
- Practice drawing architectures
- Think in terms of real-world scenarios
- Always consider the 5 pillars of Well-Architected Framework

---

*Last Updated: November 2024*  
*For: VIT Chennai - BCSE355L Cloud Architecture Design*
