# Module 4 Deep Dive on the Operational Excellence Pillar

There is 6 pillars of Well-Architected:

  - Operational Excellence
  - Security
  - Reliability
  - Performance Efficiency
  - Cost Optimization
  - Sustainability

Operational Excellence: Ability to support workloads effectively, gain insight on operations, and improve supporting proceses to deliver buisness value.

Op Ex Design Priciples:
  - Perform operations as code.
  - Make frequent, small, reversible changes.
  - Refine operartions procedures frequently.
  - Anticipate failure.
  - Learn from all operational failures.

## Op Ex Best Practices

Op Ex Best Practices Focus Areas:
  - Organization
  - Prepare
  - Operate
  - Evolve

## Organization Focus Area

Organization Priorities
  - Evaluate external customer needs
  - Evaluate internal customer needs
  - Evaluate governance requirements
  - Evaluate compliance requirements
  - Evaluate threat landscape
  - Evaluate trade-offs
  - Manage benefits and risks

Operating Models:
  - Application Engineering
  - Application Operations
  - Platform Engineering 
  - Platform Operations

Application Engineering: Business software that is custom developed or commerical off the shelf that that developed, built, and tested.
Application Operations: Deploying buisness software and then operating and managing applications in production.
Platform Engineering: Building infrastructure that the Application will run on such as Computer, Network, Storage, etc.
Platform Operations: Mantaining and supporting the platform in production.

### Organization Culture
Provide support for team members so they can be more effective at operating:
  - Executive Sponsorship
  - Team members are empowered to take action when outcomes are at risks
  - Escalation is encouraged
  - Communications are timely, clear, and actionable
  - Experimentation is encouraged
  - Team members are empowered, encouraged to maintain and grow skill sets
  - Resource teams appropriately
  - Diverse opinions are encouraged and sought within and across teams

## Prepare Focus area

### Design Telemetry
Design your workload so it provides information necessary for you to understand its internal state:
  - Implement application telemetry
  - Implement and configure workload telemetry
  - Implement user activity telemetry
  - Implement dependency telemetry
  - Implement transaction traceability

### Design for Operations

  - Use version control
  - Test and validate changes
  - Use configuration management systems
  - Peform patch management
  - Share design standards
  - Implement practices to imporve code quality
  - Use multiple environments
  - Make frequent, small, reversible changes
  - Fully automate integration and deployment

### Mitigate Deployment Risks
  - Plan for unsuccessful changes
  - Test and Validate Changes
  - Use Deployment Management Systems
  - Test Using Limited Deployments
  - Deploy using parallel environments
  - Deploy frequent, small, reversible changes
  - Fully automate integration and deployment
  - Automate testing and rollback

### Operational Readiness and Change Management
Evaluate the operational readiness of your workload, processes, procedures, and personnel to understand the risks and manage change with consistant process.
The Checklist of managing change:
- Ensure personnel capability
- Ensure a consistent review of operational readiness
- Use runbooks to perform procedures
- Use playbooks to investigate issues
- Make informed decisions to deploy systems and changes
- Facilitate support plans for production workloads

Runbooks are documented processes to achieve outcomes and playbooks are processes used to investigate an incident.

ORR (Operational Readniness Reviews) is an Amazon developed mechanism that uses requirements checklists and self-service to validate that teams can safely operate their workloads.
Security, goverance, and compliance requirements can also be included in an ORR.

A pre-mortem an exercise where a team simulates a failute to develop mitigation strategies. Use it to anticipate failures and create procedures where appropriate.

## Operate Focus Area

### Understand Workload Health
Use workload metrics to gain visiability of workload health easily. Use the metrics to create dashboards with tech and business viewpoints to help drive decisions.

- Identify key performance indicators
- Define workload metrics
- Collect and Analyze workload metrics
- Establish workload metrics baselines
- Learn expected patterns of activity for workload
- Alert when workload outcomes are at risk
- Alert when workload anomalies are detected
- Validate the achievement of outcomes and KPI and metric effectiveness

### Understanding Operational Health
You might want to use metrics based on operations outcomes to gain useful insights. You should use these metrics to implement dashboards with business and technical viewpoints that will help drive decisions

Identify KIP based on desired business outcomes such as new features, and customer outcomes such as customer support cases.
Evaluate KPIs to determine operations success
Define operations metrics to measure the achievement of KPIs for example, successful deployments and failed deployments.

Define operations metrics to measure the health of operations activities such as mean time to detect an incident, or MTTD, and mean time to recovery, or MTTR, from an incident.

Evaluate metrics to determine if operations are achieving desired outcomes, and to understand the health of your operations activities.

Perform regular proactive reviews of metrics to identify trends and determine where appropriate responses are needed

You should aggregate log data from your operations activities and operations API calls, into a service such as CloudWatch Logs.

Alert when operations are at risk. If at risk, an alert must be raised and acted upon. Operations outcomes are any activity that supports a workload in production. Succh as deploying new versions of app to outage recovery.

If alert is raised, a reference to cooresponding runbook or playbook should be included. Alerts without action can lead to alert fatigue.


# Deep Dive on the Security Pillar

What is the Security Pillar?

The security pillar encompasses the ability to protect data, systems, and assets to take advantage of cloud technologies to improve your security

## Security Design Prinicples

- Implement a strong identity foundation
- Turn on traceability
- Apply security at all layers
- Automate security best practices
- Protect data in transit and at rest
- Keep people away from data
- Prepare for security events

## Security Best Practices Areas

- Security Foundations
- Identity and access management
- Detection
- Infrastructure protection
- Data protection
- Incident response
- Application security

### Security Foundations

Shared model is used to delinate customer and AWS responsibility in cloud

Customer in charge of guest os and firewall rules

customer = Responsible for Security 'in' the cloud

AWS = Responsible for Security 'OF' the cloud

Customer choose encryption and 

Manage seperate workloads in individual accounts and group accounts in AWS

Secure account root user and properties

AWS accounts are hard boundaries and account-level permissions is recommended because it provides a strong isolation boundary for security, billing, and access

Root account might not be able to be secured with security policies sometimes

Steps to prevent inadvertent exposure of root credentials and subsequent compromise of the cloud environment:

1. Deactivate programmatic access to the root user
2. Establish appropriate controls for the root user
3. Avoid routine use of the root user

#### Operating Your Workloads Securely

- Identify and validate control objectives
- Keep up to date with security threats
- Stay current on security recommendations
- Automate testing and validation of security controls in pipelines
- Identify threats and prioritize mitigations using a threat model
- Evaluate and implement new security services and features regularly

### Identity and Access Management

Two typs of IAM:

- Identity Management
- Permissions Management

#### Identity Management

There are two idenities you must manage:

- Human Identities
- Machine Identities

Best practices for identity management:

- Use strong sign-in mechanisms
- Employ temporary credentials
- Store and use secrets securely
- Reply on a centeralized identity provider
- Audit and rotate credentials periodically
- Set up user groups and attributes

#### Permissions Management

Manage permissions to control access to human and machine idenities that require access to AWS and your workloads

Permissions control who can access what and when

Set permissions to specific human and machine identities

Best Practices for Permissions Management

- Define access requirements
- Grant least privilege access
- Establish emergency access processs
- Reduce permissions continuously
- Define permission guardrails for your organization
- Manage access based on lifecycle
- Analyze public and cross-account access
- Share resources securely in your organization
- Share resources securely with a third party

## Detection

Detection Best Practices:

- Configure service and application logging
- Analyze logs, findings, and metrics centrally
- Automate response to events
- Implement actionable security events

## Infrastructure Protection

Uses control methodology such as defense in depth, that are necessary to meet best practices and organizational or regulatory obligations

Use of these methodologies is critical for successful ongoing operations in the cloud

Infrastructure protection is a key part of an information security program 

It helps ensure that systems and services in your workload are protected against unintended and unauthorized access and potential vulnerabilities

### Protecting Networks

Users, both in your workforce and your customers, can be located anywhere

You need to pivot from traditional models of trusting anyone and employ a Zero Trust approach

Zero trust security is a model where application components or microservices are considered discrete from each other and nothing trusts any other

Best practices for protecting networks:

- Create network layers
- Control traffic at all layers
- Automate network protection
- Implement inspection and protection

### Protecting compute

Compute resources include EC2 instances, containers, lambda functions, database services, Internet of Things, and more

Each resources requires different approaches to secure them

Common strategies to consider for all of them: Defense in depth, vulnerability management, reduction in attack surface, and operation and performing actions at a distance

Best practices for protecting compute:

- Perform vulnerability management
- Reduce attack surface
- Implement managed services
- Automate compute protection
- Help people perform actions at a distance
- Validate software integrity

## Data Protection

Before architecting any workload, practicces that influence security should be in place

For example, data classification provides a way to categorize data based on levels of sensitivity

Encryption protects data by rendering it unintelligible to unauthorized access

These methods are important because they support objectives such as limiting mishandling or helping comply with regulatory obligations 

With AWS, there are a number of different approaches you can use when addressing data protection
 
### Classify data

Data classification provides a way to categorize organizational data based on criticality and sensitivity

This can help you determine appropriate protection and retention controls

It is critical to understand the type and classification of data your workload is processing, the associated business processes, where the data is stored, and who the data owner is 

You should also have understanding of the applicable legal and compliance requirements of your workload, and what data controls need to be enforced

Best Practices for classifying data:

- Identify data in your workload
- Define data protection controls
- Automate identification and classification
- Define data lifecycle management

### Protecting Data At Rest

Data at rest represents any data that you persist in nonvolatile storage for any duration in your workload

This includes block storage, object storage, databases, archives, IoT devices, and any other storage medium on which data is persisted  

Protecting your data at rest reduces the risk of unauthorized access, when encryption and appropriate access controls are implemented

Best Practices for protecting data at rest:

- Implement secure key management
- Enforce encryption at rest
- Automate data-at-rest protection
- Enforce access control
- Use mechanisms to keep people away from data

### Protecting Data in Transit

Data in transit is any data that is sent from one system to another

This includes communication between resources in your workload and also communication between other services and your end users

By providing the appropriate level of protection for data in transit, you protect the confidentiality and integrity of your workoad's data

Best Practices for protecting data in transit

- Implement secure key and certificate management
- Enforce encryption in transit
- Automate detection of unintended data access
- Authenticate network communications

## Incident Response

Even with extremely mature preventive and detective controls, your organization should still put processes in place to respond to and mitigate the potential impact of security incidents

The architecture of your workload strongly affects the ability of your teams to operate effectively during an incident to isolate or contain systems and restore operations to a known good state

### Design goals of cloud response

The general processes and mechanisms of incident response, such as those defined in the NIST SP 800-61 Computer Security Incident Handling Guide, are important

- Establish response objectives
- Document plans
- Respond using the cloud
- Know what you have and what you need
- Use redeployment mechanisms
- Automate where possible
- Choose scalable solutions
- Learn and improve your process
  

## Educate 

Automated processes help organizations spend more time focusing on measures to increase the security of their workloads

Automated incident response also makes humans avaliable to correlate events, practice simulations, devise new response procedures, perform research, develop new skills, and test or build new tools

Desite increased automation your team, specialists, and responders in a security organization still require continuous education

It is helpful to review and incorporate the following areas when thinking about educating your security teams:

- Development skills
- AWS services
- Application awareness

# Module 6 Deep Dive on the Reliabiility Pillar

## Reliability design principles

- Automatically recover from failure
- Test recoverty procedures
- Scale horizontally to increase aggregate workload availability
- Stop guessing capacity
- Manage change in automation

## Reliability Best Practices

- Foundations
- Workload architecture
- Change management
- Failure management

## Foundations

In the foundations best practice area, scope can extend beyond a single workload or project  

It needs to be understood and in place before architecting any system

If you don't, you might face long lead times and blockers along the way

Get these taken care of early so you can be free to change resource size and allocation on demand

In this section, you will learn how to manage service quotas or constraints and plan your network topology

### Manage service quotas and constraints

- Stay aware of service quotas and constraints
- Manage service quotas across accounts and regions
- Accommodate fixed service quotas and constraints through architecture
- Monitor and manage quotas
- Automate quota management
- Ensure a sufficient gap exists between current quotas and maximum usage

### Plan your network topology

- Use highly avaliable network connectivity for your workload public endpoints
- Provision redundant connectivity between cloud and on-premises environments
- Ensure IP subnet allocation accounts for expansion and availability
- Prefer hub-and-spoke topologies over many-to-many mesh
- Enforce non-overlapping private IP ranges in connected address spaces

## Workload Architecture

A reliable workload starts with upfront design decisions for both software and infrastructure

Your architecture choices will impact your workload behavior across all six AWS Well-Architected pillars

For reliability, there are certain patterns to choose

### Design your workload service architecture

- Choose how to segment your workload
- Build services focused on specific business domains and functionality
- Provide service contracts per API

### Design interactions in a distributed system to prevent failures

Distubuted systems rely on communications networks to interconnect components, such as servers or services

Your workload must operate reliably despite data loss or latency in these networks

Components of the distributed system should operate in a way that does not negatively impact other components of the worload

These best practices can help prevent failures and improve mean time between failures, or MTBF:
- Identify which kind of distrubuted system is required
- Implement loosely coupled dependencies
- Do constant work
- Make all responses idempotent

## Design Interactions in a distributed system to mitigate or withstand failures

- Implement graceful degradation to transform hard dependencies to soft
- Throttle requests
- Control and limit retry calls
- Fail fast and limit queues
- Set client timeouts
- Make services stateless where possible
- Implement emergency levers

## Change Management

Changes to your workload or its environment must be anticipated and accommodated to achieve reliable operation of the workload

Changes include those imposed on your workload such as spikes in demand 

They also include those from within, such as feature deployments and security patches

### Monitor workload resources

- Monitor all components for the workload (generation)
- Define and calculate metrics (aggregation)
- Send notifications (real-time processing and alarming)
- Automate responses (real-time processing and alarming)
- Perform analytics
- Conduct reviews regularly
- Monitor end-to-end tracing of requests through your system

### Design a workload to adapt to changes in demand

- Use automation when obtaining or scaling resources
- Obtain resources upon detection of impairment to a workload
- Obtain resources upon detection that more resources are needed for a workload
- Load test your workload

### Implement Change

Controlled changes are necessary to deploy new functionality and help ensure that the workloads and operating environment are running known and properly patched software

If these changes are uncontrolled then it makes it difficult to predict the effect of these changes or address issues that arise because of them

- Use runbooks for standard activities such as deployment
- Integrate functional testing as part of your deployment
- Integrate resilency testing as part of your deployment
- Deploy using immutable infrastructure
- Deploy changes with automation

## Failure Management

Low-level hardware component failures are something to be dealt with every day in an on-premises data center

In the cloud, however, you should be protected against most of these types of failures

Regardless of your cloud provider, there is the potential for failures to impact your workload

Therefore, you must take steps to implement resilence

A prerequiste to applying the best practices discussed here is that you must ensure that the people designing, implementing, and operating your workloads are aware of business objectives and the reliability goals to achieve these

These people must be aware of and trained for these reliability requirements

### Back up data

Back up data, applications, and configurations to meet requirements for recovery time objectives (RTO) and recovery point objectives (RPO)

- Identify and back up all data that needs to be backed up
- Secure and encrypt backups
- Perform data backup automatically
- Perform periodic recovery of data to verify backup integrity and processes

### Use fault isolation to protect your workload

Fault-isolated boundaries limit the effect of a failure inside a workload to a limited number of components

Components outside of the boundary are unaffected by the failure

Using multiple fault isolated boundaries, you can limit the impact on your workload

- Deploy workload to multiple locations
- Select appropriate locations for your multi-location deployment
- Automate recovery for components constrained to a single location
- Use bulkhead architectures to limit scope of impact

### Design workload to withstand component failures
Workloads with a requirement for high avaliability and low mean time to recovery, or MTTR, must be architected for resilency

- Monitor all components of workload to detect failures
- Fail over to healthy resources
- Automate healing on all layers
- Rely on data plane, not control plane, during recovery
- Use static stability to prevent bimodal behavior
- Send notifications when events impact avaliability
- Architect product to meet availiability targets and uptime SLAs

### Test reliability

After designing your workload to be resilient to production stresses, testing is the only way to ensure that it will operate as designed to deliever the resilency you expect

Test to validate your workload meets functional and nonfunctional requirements because bugs or performance bottlenecks can impact its reliability

- Use playbooks to investigate failures
- Perform post-incident analysis
- Test functional requirements
- Test scaling and performance requirements
- Test resilency using chaos engineering
- Conduct game days regularly

### Plan for Disaster recovery

Having backups and redundant worload components in place is the start of your disaster recovery strategy

- Define recovery objectives for downtime and data loss
- Use defined recovery strategies to meet recovery objectives
- Test disaster recovery implementation to validate implementation
- Mange configuration drift at the DR site or Region
- Automate recovery

# Module 7 Deep Dive on the Performance Efficiency Pillar

## What is the performance efficiency pillar?

The performance efficency pillar focuses on the efficent use of computing resources to meet requirements, and how to maintain efficiency as demand changes and technologies evolve.

## Performance Efficency Design Principles

- Democratize advanced technologies
- Go global in minutes
- Use serverless architectures
- Experiment more often
- Consider mechanical sympathy

## Performance Efficiency Best Practices

- Selection
- Review
- Monioring
- Trade-offs

### Selection

#### Performance architecture selection

For performance architecture selection, use a data-driven approach to select the patterns and implementation for your architecture and achieve cost-effective solution

Your architecture will likely combine a number of architectural approaches

The implementation of your architecture will use services that are specific to the optimization of your architecture performance 

- Understand the avaliable services and resources
- Define a process for architectural choices
- Factor cost requirements into decisions
- Use policies or reference architectures
- Use guidance from your cloud provider or an appropriate partner
- Benchmark existing worloads
- Load test your worload
  
#### Compute architecture selection

When selecting a compute architecture use resources that meet your requirements and performance needs while providing great efficiency of cost and effort

This can help you accomplish more with the same number of resources

But, the optimal compute solution for a workload will always vary based on your application design, usage patterns, and configuration settings 

- Understand avaliable compute configuration options
- Evaluate avaliable compute options
- Collect compute-related metrics
- Determine required configuration by rightsizing
- Use avaliable elasticitty of resources
- Continually evaluate compute needs based on metrics

#### Storage architecture selection

The optimal storage solution for a system varies based on the kind of access method, which could be block, file, object, and based on if the patterns of access are random or sequential.

It also depends on needed throughput and avaliabilty and durability constraints

It could also differ based on frequency of access or frequency of update

- Understand storage characteristics and requirements
- Make decisions based on access patterns and metrics
- Evaluate avaliable configuration options

#### Database architecture selection

Choosing the wrong database solution and features for a system can lower performance efficiency

Therefore, when deciding for an optimal database solution, it is important to consider the requirements 

Examples include avaliblity, consistency, partition tolerance, latency, durability, scalability, and query capability

- Understand data characteristics
- Evaluate the availiable options
- Collect and record database performance metrics
- Choose data based on access patterns
- Optimize data storage based on access patterns and metrics

#### Network architecture selection

Network architecture selection can have great impacts (both positive and negative) on workload performance and behavior, because the network is between all workload components

There are also workloads that are heavily dependent on network performance such as high-performance computing (HPC) in which deep network understanding is important to increase cluster performance

You must detertime the workload requirements for network latency, jitter, and throughput

- Understand how networking impacts performance
- Evaluate avaliable networking features
- Choose appropriately sized dedicated connectivity or VPN for hybird workloads
- Leverage load-balancing and encryption offloading
- Choose network protocols to improve performance
- Choose your workload's location based on network requirements
- Optimize network configuration based on metrics

### Review

#### Evolve your workload to take advantage of new releases

- Stay up-to-date on new resources and services
- Define a process to improve workload performance
- Evolve workload performance over time

### Monitoring

#### Monitoring resources to ensure expected performance

- Record performance-related metrics
- Analyze metrics when events or incidents occur
- Establish KPIs to measure workload performance
- Use monitoring to generate alarm-based notifications
- Review metrics at regular intervals
- Monitor and alarm proactively

### Trade-Offs

#### Using trade-offs to improve performance

- Understand areas where performance is most critical
- Learn about design patterns and services
- Identify how trade-offs impact customers and efficiency
- Measure impact of performance improvements
- Use various performance-related strategies

# Module 8 Deep Dive on the Cost Optimization Pillar

## What is the cost optimization pillar?

A cost-optimized workload fully utilizes all resources, achieves an outcome at the lowest possible price point, and meets your functional requirements

## Cost Optimization Design Principles

- Practice Cloud Financial Management (CFM)
- Adopt a consumption model
- Meature overall efficiency
- Stop spending money on undifferentiated heavy-lifting
- Analyze and attribute expenditure

## Cost Optimization Best Practice Areas

- Practice Cloud Financial Management
- Expenditure and usage awareness
- Cost-effective resources
- Management of demand and supply resources
- Optimization over time

### Practice Cloud Financial Management

Practicing cloud financial management, or CFM, helps organizations realize business value and financial success as they optimize their cost and usuage to scale on AWS

- Establish a cost optimization function
- Establish a partnership between finance and tech
- Establish cloud budgets and forecasts
- Implement cost awareness in your org process
- Report and notify on cost optimization
- Monitor cost proactively
- Keep up-to-date with new service releases
- Create a cost-aware culture
- Quantify business value from cost optimization

## Expenditure and Usage Awareness

Understanding your organization's costs and drivers is critical to manage your cost and usage effectively and identify cost-reduction opportunities

Organizations typically operate multiple workloads run by multiple teams

These teams can be in different organization units, each with its own revenue stream

The capability to attribute resource costs to the workloads, individual organization, or product owners drives efficient usage behavior and helps reduce waste

Accurate cost and usage monitoring helps you understand how profitable organization units and products are

You can then make more informed decisions about where to allocate resources in your organization 

Awareness of usage at all levels in the organization is key to driving change, as change in usage drives changes in cost

### Governance

Governance is used to establish policies and mechanisms to ensure appropriate costs are incurred while objectives are achieved

By employing a checks-and-balances approach to governance, you can innovate without overspending

- Develop policies based on your organization's requirements
- Implement goals and targets
- Implement an account structure
- Implement groups and roles
- Implement cost controls
- Track project lifecycles

### Monitor Cost and Usage

Monitor cost and usuage to establish polcies and procedures to monitor and appropriately allocate your costs

This helps you measure and improve the cost efficency of this workload

- Configure detailed information sources
- Add organization information to cost and usage
- Identify cost attribution categories
- Establish organization metrics
- Configure billing and cost management tools
- Allocate costs based on workload metrics
  
### Decommission resources

Decommission resources to implement change control and resource management from project inception to end of life

This helps ensure that you shut down or terminate unused resources to reduce waste

- Track resources over their lifetime
- Implement a decommissioning process
- Decommission resources
- Decommision resources automatically
- Enforce data retention policies

## Cost-effective resources

Using the appropriate services, resources, and configurations for your workloads is key to cost savings

### Evaluate cost when selecting services

Amazon Elastic Compute Cloud, or Amazon EC2, Amazon Elastic Block Store, or Amazon EBS; and Amazon Simple Storage, or Amazon S3; are building-block AWS services

Managed services such as Amazon Relational Database Service, or Amazon RDS, and Amazon DynamoDBm are higher-level, or application-level, AWS services

By selecting the appropriate building blocks and managed services, you can optimize a workload for cost

For example, using managed services, you can reduce or remove much of your administrative and operational overhead, freeing you to work on applications and business-related activities

- Identify organization requirement for cost
- Analyze all workload components
- Perform through analysis of each component
- Select software with cost-effective licensing
- Selct components to optimize cost in line with organization priorities
- Perform cost analysis for different usage over time

### Select correct resource type, size, and number

Select correct resource type, size, and number to ensure that you have the appropriate configuration for the task at hand 

You minimize waste by selecting the most cost-effective, type, size, and number of resources

- Perform cost modeling
- Select resource type, size, and number based on data
- Select resource type, size, and number automatically based on metrics

# Domain 9 Deep Dive on the Sustainability Pillar

## What is the sustainability pillar?

The most recent pillar in the AWS Well-Architected Framework and is the practice of understanding impacts of services used, quantifying impacts through entire workload lifecycle, and minimizeing to reduce impacts

Focuses on environmental impacts, especially energy consumption and efficiency, since they are important levers for architects to inform direct action to reduce resource usage

Most recent pillar and was introduced in 2021 for customers to make sustainability decisions about their workloads

The sustainability best practices are understand, quantify, and apply

Sustainability would be especially important in situations like customer demand, government regulations, employee demand, impact investing, and sustainability as competetive positioning

## Sustainability Design Principles

- Understand your impact
- Estalish sustainability goals
- Maximize utilization
- Anticipate and adopt new, more efficent hardware and software offerings
- Use managed services
- Reduce the downstream impact of your cloud workloads

## Sustainability best practices

- Region Selection
- Alignment to demand
- Software and architecture patterns
- Data patterns
- Hardware and services
- Process and culture

### Region Selection

The choice of where you put your workload affects its KPIs, including performance, cost, and carbon footprint

To improve these KPIs, you should choose Regions for your workloads based on business requirements and sustainability goals

### Alignment to demand

The way users consume your workloads and other resources can help you identify improvements to meet sustainability goals

- Scale infrastructure with user load
- Align SLAs with sustainability goals
- Stop the creation and maintaince of unused assets
- Optimize geographic placement of workloads for user locations
- Optimize team member resources for activities performed
- Implement buffering or throttling to flatten the demand curve

### Software and Architecture Patterns

- Optimize software and architecture for asynchronous and scheduled jobs
- Remove or refactor workload components with low or no use
- Optimize areas of code that consume the most time or resources
- Optimize impact on customer devices and equipment
- Use software patterns and architectures that support data access and storage patterns

### Data Patterns

- Implement a data classification policy
- Use technologies that support data access and storage patterns
- Use policies to manage the lifecycle of your datasets
- Use elasticity and automation to expand block storage or file system
- Remove unneeded or redundant data
- Use shared file systems or object storage to access common data
- Minimize data movement across networks
- Back up data only when difficult to recreate

### Hardware and Services

Look for ways to reduce workload sustainability impacts by making changes to your hardware management practices

- Use the minimum amount of hardware to meet your needs
- Use instance types with the least impact
- Use managed services
- Optimize your use of hardware-based compute accelerators

### Process and Culture

- Adopt methods that can rapidly introduce sustainability improvements
- Keep your workload up-to-date
- Increase utilization of build environments
- Use managed device farms for testing
