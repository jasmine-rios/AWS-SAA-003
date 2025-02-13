# Compute Workloads
- Amazon Elastic Compute Cloud (EC2)
- Amazon Elastic Kubernetes Service (EKS)
- Amazon Elastic Container Service (ECS)
- AWS Lambda

# Database Workloads
- Amazon Relational Database Service (Amazon RDS)
- Amazon DynamoDB - NoSQL DB Low latency performance at extreme scale
- Amazon Aurora - Cloud native relational database services
- Amazon Redshift - Data warehouse needs

# Resilancy in Database
- Amazon RDS uses read replica or multi-az design for resilence but does not replace cache
- DynamoDB uses Amazon DynamoDB Accelerator (DAX) as cache
- DyanoDB, Amazon CloudFront, Amazon ElastiCache use cache
- Edge networking services for resilance Cloudfront, Route 53, AWS Global Accelerator

# Workloads
- If you wanted a file share without dealing with maintance and design, you could use AWS Transfer Family
- AWS Transfer Family gives you the ability to create and modify data transfer and data processing without maintaining code or infrastructure
- AWS Transfer Family is backed to 3 AZs and backed by autoscaling
  
# Severless

- **Compute**: AWS Lambda
- **Containers**: AWS Fargate
- **Application Integration**: Amazon SQS, Amazon SNS, Amazon EventBridge, AWS Step Functions, AWS AppSync
- **Storage**: Amazon S3
- **Database**: Amazon DynamoDB, Amazon RDS Proxy, Amazon Aurora Serverless 

# Decoupling Techniques

- Synchronous decoupling involves components that must always be avaliable for proper functionality
- Asynchronous Decoupling involves communication between components through durable components

- Elastic Load Balancing (ELB)
- Amazon Simple Quenue Service (Amazon SQS)
- Amazon EventBridge 
- Amazon DynamoDB

# Disaster recovery strategies

active/passive:

- Backup & Restore
- Pilot Light
- Warm Standby

active/active

- Multi-site active/active

## Backup and Restore

- RPO/RTO: Hours
- Lower priority
- Provision all AWS resources after event
- Restore backups after event
- Cost: $

## Pilot Light

- RPO/RTO: 10s of minutes
- data live
- Provision some AWS resources and scale after event
- Cost: $$

## Warm Standby

- RPO/RTO: Minutes
- Always running, but smaller
- Business Critical
- Scale AWS resources after event
- Cost $$$

## Multi-Site active/active

- Zero downtime
- Near zero data loss
- Mission Critical Services
- Cost $$$$

# Things to look into
- RDS has multi-az deployment capability for fail tolerance for RTO of 35 seconds

- Amazon Aurora database uses cross region failover and takes to failover?

- Amazon DynamoDB uses global tables?

- Back up and recovery options for RDS? Aurora, DyanamoDB?

Image Builder for EC2?

VPC Peering connections, AWS Transit Gateways, AWS site-to-site VPN, AWS Direct Connect, AWS Direct Connect Gateways, and Amazon Route 53 Resolver?

Capabilities and downfalls? 
Automate Deployments using services like Elastic Beanstalk, CloudFormation, and OpsWorks?

For container deployments use ECS and EKS

Use Amazon Inspector and Amazon CodeGuru to find vulnerabilities and scan code

Failover to other side of the world? Know capabilities of Amazon Route 53 like failover routing

Global Accelerator for app avaliability and performance

RDS proxy for a fully managed, highly avaliable for making applications more scalable, more resilient to database failures, and more secure

Serverless applications for a large number of open connections to the database server and may open and close db connections at a high rate and exhausting database memory and compute resources

RDS Proxy allows you to pull and share connections established with the database to improve db efficency and application scalability
