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

