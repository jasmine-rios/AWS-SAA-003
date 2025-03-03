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







