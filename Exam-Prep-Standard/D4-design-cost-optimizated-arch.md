# Domain 4 Design Cost-Optimized Architectures

## Design Cost-Optimized Storage Solutions

- Amazon S3 **Object Storage**
- Amazon EBS **Block Storage**
- Amazon EFS **File Storage**

For EBS to save money, make sure you are right-sizing your volumes

### Storage Cost Optimization

- Amazon EC2: Instance Store and Volume
- Amazon S3: S3 Glacier

Instance store is for ephemeral or data will not be saved and is used for fast processing scenarios

EBS Volumes attached to an instance is okay for normal peristent storage situations and is non-emphermeral or not disappearing

EBS gives EC2 the ability to write to block level devices that can be migrated to different instances and snapshots for migration

Emphermel storage for EC2 is included in hourly rate and Amazon EBS comes at additional cost

### Visability for Cost Optimization

- Amazon Cloudwatch: alarm and Rule
- AWS Trusted Advisor
- AWS Well-Architected Tool
- AWS Cost Explorer
- AWS Cost and Usage Report
- AWS Organizations
- AWS Control Tower

How do you use cost allocation tags?
- One way is to use tags to filter views in Cost Explorer to help analyze cost

Cost explorer is for high level view and then you can break into small

Cost and Usage reports break down costs by time, product, resource tags, etc

AWS Budgets allows you to create alarms

Can use automated actions based on defined budget thresholds

AWS Organization and AWS control Tower allow consolidated billing across accounts

A tip is to look at optimizing EBS by looking at how many IOPS you are using compared to what you are paying for

Amazon Data Lifecycle Manager and Backup to learn more solutions for deleting old EBS snapshots or backups for other 

## Design Cost-Optimized Compute Solutions

### Compute Workloads

Services:

- Amazon EC2: On-demand instance, savings plans, reserved instance, spot instance
- Amazon Elastic Container Service (Amazon ECS)
- AWS Lambda
- AWS Compute Optimizer

### Cost Optimization Pillar

- Right-sizing
- Increased elasticity
- Choose the right pricing model
- Match storage to usage
- Measure and monitor

### Compute Workloads

- Elatic Load Balancing: Application Load Balancer **(ALB)**, Network Load Balancer **(NLB)**, Classic Load Balancer, **Gateway** Load Balancer
- Auto Scaling: Get the Auto Scaling Group (ASG) with EC2 instances to expand horizontally based on load balancer metric or health checks

Know cost optimization best practices on load balancer

## Design Cost-Optimized Database Solutions

- Amazon RDS (RDS read replica and Amazon RDS proxy instance
- Amazon Aurora
- Amazon DynamoDB: Amazon DynamoDB Accelerator (DAX)
- Amazon ElastiCache
- Amazon CloudFront
- Amazon Route 53
- Amazon Global Accelerator

Know the type of data stores

Relational Database Management Systems are at the core of most processing systems but you do not want to store all your data in an RDS management system

If you store all your data in an RDS management system you will and increase your total cost of ownership

To determine data store by looking at the access patterns, the expected scale/growth, and how often your data will be accessed 

A tips for migrating database to AWS with less cost:
- Moving a subset of the relational database to EC2 or RDS
- Moving large objects from relational db to S3
- Moving a subset of the relational database to a no SQL data store such as dynamodb

Will schema be fixed through lifecycle?


## Design Cost-Optimized Network Architectures

