# Determine high-performing and elastic compute solutions

Four layers

- Compute
  
- Storage
  
- Database
  
- Network

## Storage forms

- Block (EBS)
  
- Object (S3)

- File (EFS)

Learn scaling for each, i.e. EBS scales differently than others because you scale the volume (volume type, size, and IOPS capacity)

EBS scaling is manual but supports live configuration changes when in prod

EFS scaling vertically is done automatcially as you add and remove files (Least amount of operational work)

## File storage to know

AWS Storage Gateway- Help you move files to EFS from on-premises for hybrid storage solutions

Amazon FSx - File server similar to EFS but for Linux and for hybrid solutions too
It is a fully-managed Windows file system share drive, supports SMB and NTFS, and supports AD integration 

EFS is great for large repositories, development enivornment, media storage, and more

### Key words for EFS

- network-based file systems
- NFS
- Hybrid Access (VPN or Direct Connect)
- Linux instances

Configuration of EFS for performance - General Purpose and Max IO 

### Cost optimization lifestyle policies

Data isn't static, once you operate your applications over time the rate of data accumilation should be considered when making arch decisions ( 1 TB this year 10 T next year

## Object storage to know

- S3 storage classes
- Basic API calls
- Multi-part uploads

S3 is good for large data storage and backup/recovery 

Understand scalability, avaliabilty, durability, security, performance, and cost optimization with S3

S3 is global service and ran in every AWS Region

Your S3 data is stored in a region and is replicated for Avaliabilty Zone fault tolerance and can be replicated in another region

For data upload or transfers, you can improve the performance in S3 with S3 Accelerator for more performant uploads and caching with Cloufront

## Block Storage to know

Know EBS volume types their performance, use cases, and IOPS 

EBS volumes are extermely low latency and the performance is configurable

EC2 has two storage: instant store (local store and ephemeral) and EBS volumes (persistant storage) 

EBS snapshots for EBS for backup and disaster recovery and stored in S3 and becomes region resilient 

### Key words for EBS:

- DAS
- SAN 
- Perisistant Storage for EC2 

# Design high-preforming and elastic compute solutions

Just because a service is hosted on AWS doesn't mean that it is scalable by default, depends on your design

## Compute areas

- Instances (EC2)
- Containers (ECS and EKS)
- Functions (Lambda)

### Containers

EKS allows AWS-powered kubernetes to run on EC2 instances

ECS has two types: fargate and EC2 instance

Fargate serverless compute for containers and EC2 can be used to control the installation, configuration, and management of your compute environment

Learn how to intergrate other services with your containers such as application load balancers for port mapping 

Understand functions how to extract the execution environment from the code you want to run

Lambda accepts functions with a small piece of code written in a language

Lambda uses a runtime such as Python, Java, NodeJS, etc and starts the code without running an EC2 instance

You are billed for execution time of functions and functions are invoked based on event

Lambda functions have a 15-minute execution limit; use Step Functions for anything longer

You can use lambda with Cloudfront to run Lamabda globally by deploying functions to all Cloudfront edge locations

## Domain 3.2 Focus areas

Know how to decouple workloads so components can scale independently

Identify metrics and conditions to perform scaling actions

Select the appropiate compute options and features (for example, EC2 instance types) to meet business requirements

Select the appropriate resource type and size (for example, the amount of lambda memory) to meet buisness requirements

Services:

- Amazon Simple Quenue Service (Amazon SQS)
- Amazon Simple Notification Service (Amazon SNS)
- Amazon Cloudwatch
- Elastic Load Balancer
- Amazon Elastic Compute Cloud (Amazon EC2)
- AWS Lambda

## To knows 

There are useful metrics that are not automatically tracked by Cloudwatch such as amount of memory used by EC2

You can use custom metrics for scaling or metrics related to elastic load balancing like HealthyHostCount and your SurgeQuenueLength 

Lambda is scalable automatically but EC2 is not inheritly scalable by default

Amazon EC2 instance types:

- General Purpose Instances
    Balance of compute, memory, and networking resources;
    use cases for web servers and code repositories;
    ex M8g.medium: 1 vCPU, 4 GiB memory, EBS-only storage, up to 12.5 Gbps network bandwidth)
  
- Compute Optimized Instances
    compute-bound applications that benefit from high-performance processors;
    use cases for batch processing, media transcoding, and high-performance web servers;
    C8g.medium: 1 vCPU, 2 GiB memory, EBS-only storage, up to 12.5 Gbps network bandwidth
  
- Memory Optimized Instances
    deliver fast performance for workloads that process large data sets in memory;
    open-source databases and real-time big data analytics;
    R8g.medium: 1 vCPU, 8 GiB memory, EBS-only storage, up to 12.5 Gbps network bandwidth
  
- Storage Optimized Instances
    for workloads that require high, sequential read and write access to very large data sets on local storage;
    They are optimized to deliver tens of thousands of low-latency, random I/O operations per second (IOPS);
    I4g.large: 2 vCPU, 16 GiB memory, 1 x 468 GB NVMe SSD, up to 10 Gbps network bandwidth

- Accelerated Computing Instances
    use hardware accelerators, or co-processors, to perform functions such as floating-point number calculations, graphics processing, or data pattern matching more efficiently than software running on CPUs;
  P5.48xlarge: 8 NVIDIA H100 GPUs, 192 vCPUs, 2 TiB memory, 8 x 3.84 TB NVMe SSD, 3200 Gbps network bandwidth
  
- High-Performance Computing (HPC) Instances
    Purpose-built to offer the best price performance for running HPC workloads at scale on AWS;
    Ideal for large, complex simulations and deep learning workloads
    Hpc7g.4xlarge: 16 physical cores, 128 GiB memory, EBS-only storage, 200 Gbps EFA network bandwidth

- Burstable Performance Instances
    provide a baseline level of CPU performance with the ability to burst above the baseline
    general-purpose workloads such as web servers and small databases
    T3.medium: 2 vCPUs, 4 GiB memory, EBS-only storage
  
  ## Determine High-Performing Database Solutions 3.3

  You can choose from multiple purpose-driven database solutions

  - Relational
  - Key Value
  - Document
  - In-memory
  - Graph
  - Time Series
  - Ledger Databases
    
You don't have to worry about provisioning and mantaining servers

AWS continously monitors your clusters to keep your workloads up and running

Has self-healing storage and automated scaling

Database you choose is based on availability, consistency, partition tolerance, latency, durability, scalability, and query capability

Many systems use different databases for subsystems

## Domian 3.3 Focus Areas

- Design database architectures
- Determine an appropriate database engine
- Determine an appropriate database type
- Integrate caching to meet buisness requirements
- Configure read replicas to meet business requirements

Services:
- Amazon Redshift
- Amazon Aurora
- Amazon DynamoDB
- Amazon Relational Database Service (Amazon RDS)
- Amazon ElastiCache

The database you choose has potential to accelerate your performance

A lot of db are chosen due to organizational defaults rather than through a data-driven approach

Know use cases, how these services work and operate instead knowing the databases

How do you maximize the performance of your relational databases?

What if traffic was mostly fromr read operations on the database?
Read replicas for RDS

Understand the purpose of read replicas compared to multi-AZ deployments

- Aurora clusters and data replication
- Database solutions
- Capacity planning

## Relational Databases
Amazon RDS has RDS proxy instance

Amazon Aurora clusters and data replication work

The cluster is made up of a single primary instance and zero or more read replicas

Provide the benefits of reads and multi-az to improve avaliability and read operations on your cluster

If you were running a lambda as your compute that open many different connections to your RDS instance

Use RDS Proxy to manage connections more efficiently because it maintains a pool of established connections to your RDS instance

Thew RDS Proxy reduces stress on your compute and memory resources and supports a large number and frequency of connections for app to scale

RDS instance auto-scaling?

Storage autoscaling for an RDS instance; yes but auto scaling doesn't occur if max storage threshold would be equal to or exceeded by the storage increment

## Aurora vs RDS

Aurora is part of the RDS family but does have a few differences and improvements over RDS

The Aurora architecture is very different from RDS and uses base arch of a cluster

Aurora storage is different than RDS because Aurora does not use the local storage for compute

Instead it uses a shred cluster volume for faster provisioning and improved avaliability and better performance

If you need conistant single-digit millisecond performance and extremely high volumes what do you choose? Amazon Aurora or DynamoDB?

AWS New Release Amazon RDS for SQL Server now supports Cross Region Read Replica

Before Amazon RDS was only regional and Aurora could cross regions due to it having Aurora Global Database that can span multiple regions


## DynamoDB 

DynamoDB is known for consistent response times in the single milliseconds regardless of loading and without tuning effort

DynamoDB's data is replicated across multiple storage nodes by default and it is fast and backed by SSD

DynamoDB provides backups, point-in-time recovery, encryption at rest, and can support event-driven integration to take actions if your table changes

Amazon DynamoDB uses Amazon DynamoDB Accelerator (DAX) and adds access to data in milliseconds and has two caches: item and query

## Amazon ElastiCache

Amazon ElastiCache is an in-memory database for two caching engines: Memcached and = Redis

## Aurora Severless

Aurora Serverless is an on-demand auto-scaling configuration for Aurora that scales compute capacity up and down

Aurora serverless provides a version of the Aurora database product where you do not provision/manage the db instance and is arch differently

Aurora Serverless provides the same shared cluster storage so six copies of your data is across three avaliabilty zones but cluster provisioning is different

ACUs or Aurora Capacity Units provide a certain amount of compute and a corresponding amount of memory

We choose min ACU and max ACU and then Aurora Serverless cluster will scale between those based on load

The ACU can go down to zero and paused after a period of inactivity for cost savings

# 3.4 Determine high-performing and/or scalable network architectures

## Networking

- Fundamentals
- Services and features
- Backup and restore services
- Metrics and IaC

Services
- Amazon Virtual Private Cloud (VPC)
- Endpoints
- AWS Global Acceleratir
- Amazon Route 53
- Amazon CloudFront
- AWS Direct Connect

### Amazon VPC

What components are needed for your VPC? This is a possible build order of VPC

- VPC
- Subnets
- Route Tables
- Internet Gateway
- Network Access Control lists
- Security Groups
- Customizing the VPC by adding resources
- Update Security Groups
- Add NAT gateway if needed
- Peer to another VPC
- Create Endpoints

### VPN connections vs. Direct Connect

You can set up VPN easiest than Direct Connect but traffic goes through internet to connected network

Direct Connect keeps the traffic on AWS backbone 

### Transit Gateway

Can be used with either VPN or Direct Connect to connect multiple VPCs to a remote network

Learn how it works, use cases, and how it can simplify network peering solutions

### AWS CloudHub

Helps you create a hub and spoke model for connecting networks 

### Endpoint Services

PrivateLink to share out VPC without VPC peering overhead

VPC endpoints

Gateway endpoints are used for AWS public services and sit inside the AWS public zone

You would use gateway endpoints to connect with S3 or DynamoDB from a private instance or subnet that doesn't have internet access with no NAT gateway

### Route 53 Routing Policies

Geoproximity routing policies on Route 53 for serving content as physically close to users as possible 

Learn functionality of Route 53, how to develop solutions using it, and record types to create

### Improve Network

Global Accelerator can improve your application's network peformance

AWS edge locations allows you to cache assets closer to your end users using the CloudFront service

Learn how Cloudfront works, use cases, and benefits of using it

## Migration

Services:
- AWS Application Discovery Service
- AWS Transfer Family
- AWS DataSync
- AWS Migration Hub
- AWS Server Migration Service (AWS SMS)
- CloudEndure Migration
- AWS Migration Evaluator
- AWS Snow Family:
  - AWS Snowball Edge
  - AWS Snowmobile
  - AWS Snowball
  - AWS Snowcone

## Load Balancer

- Application Load balancer (layer 7 appplication)
- Network Load Balancer (Layer 4 Network)
- Gateway Load Balancer (Layer 5 Transportation)

# 3.5 Determine high-performing data ingestion and transformation solutions

AWS Data ingestion is a proces of getting data so collecting, curating, and preparing data from the source system to AWS for storage, data lakes, ML, etc

## Data Ingestion Patterns

There are two types:

- Homogeneous (moving source data to destination in different format and requires ETL) 
- Heterogenous (move source data to destination in the same format or same storage engine as the source)
  
### Homogeneous

- Amazon EMR
- Amazon Athena
- Amazon Relational Database Service (Amazon RDS)
- Amazon Simple Storage Solution (Amazon S3)

### Heterogeneous

- Amazon Redshift
- Amazon Relational Database Service (Amazon RDS)
- Amazon Kinesis
- AWS Glue
- Amazon Simple Storage Solution (Amazon S3)

## Kinesis

For streaming data use Amazon Kinesis and Amazon Managed Streaming for Apache Kafka;

Amazon Kinesis has the capabilities to provide the collection, processing, and analysis of data in real time

Also provides ingestion of streaming data

Producers of data push data directly into the stream which consists of a group of stored data units called records

The stored data is avaliable for further processing or storage as part of the data pipeline

Ingestion of streaming videos can be done using Kinesis video streams 

Understand the kinesis family to know which service to use for a specific scenario or use case

Why would you choose Kinesis data streams instead of Kinesis Data Fire Hose?

- Data Streams is the real time data streaming service in Kinesis with high scalability and durability
  It can help in continuous capturing multiple gigabytes of data every second from multiple sources
  
- Data Fire Hose provides a facility of loading data streams into AWS data stores
  Kinesis Data Fire Hose provides the simplest approach for capturing, transforming, and loading data streams into AWS data stores

Which Kinesis solutions includes basic data transformation options?
  - Kinesis data analytics

## Data Transformation

- Amazon EMR
- AWS Glue
- Amazon Simple Storage Service (Amazon S3)
- Data lake
- Lambda Function

Once the data is extracted, it needs to be transformed and loaded into a data store for feeding into a machine learning model

It also needs to be cataloged and organized so that it's available for consumption

What services can we use to optimize Processsing? Amazon EMR, AWS Glue, AWS Lake Formation?
- If your data is stored in S3, you could choose to use Amazon EMR or AWS Glue 
- If you have large jobs, there are best practices to optimize data access from EMR and Glue to S3.
  Remember S3 can scale horizontally and with EMR and Glue, you can process data in a highly distributed way at a massive scale
  Depending on your design, you may need to adjust the number of concurrent S3 requests, modify retry strategy for S3 request, or adjust the number of S3 objects processed  

What are the ways to optimize your data ingestion and transformation? 
- If you bill your data lake on S3 using EMR clusters you can transform your data assets to Parquet or use Lambda functions to transfer your data in a data lake built on S3 

## Data Analytics and Visualization

- Amazon Athena
- AWS Lake Formation
- Amazon QuickSight
