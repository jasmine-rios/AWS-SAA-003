## Amazon Cognito

Lets users sign in with facebook and other SAML 2.0 to your web and mobile app

## Amazon Detective

Investigates root causes of potential security issues or suspicious activities of current and future accounts

Using AWS security services such as GuardDuty, Macie, and Security hub can be used to identify security issues but not complex and deep investigations like Dectective

Uses VPC flow logs, AWS CloudTrail, and Amazon GuardDuty as data sources to create visualization of details to drill down to the root cause

## Amazon GuardDuty

Threat detection that continously monitors for bad activity and weird behavior to protect AWS accounts, workloads, Kubernetes clusters, and S3 data

Looks at unusual API calls, unauthorized deployments, and exfilterated credentials to indicate compromise.

Works with AWS Organizations for organizaion-wide analyzing of account events for signs of unauthorized use

Uses threat feeds and machine learning anomaly detection to detect anomalies in account and workload activity

It sends detailed findings to GuardDuty, CloudWatch Events, and security hub. Further investigation is done by Dectective

## Amazon Inspector

Automated vulnerability management service that continously scans AWS workkloads for software vulnerabilities and unintended network exposure

Uses across all accounts once allowed and automatically discovers running EC2 instance and container images in ECR and scans for vulnerabilities

A risk score using CVE information with factors such as network access and exploitability to prioritize the most critical vulnerabilities

Inspector uses SSM agent to eliminate the need for you to deploy a standalone agent for EC2 instance assessments.

Inspector is also integrated with ECR to support intelligent, cost-efficient, and continual vulnerability assessments of container images\

All findings are aggregated into the Amazon Inspector Console, routed to AWS Security Hub, and pushed through Amazon EventBridge to automate workflows such as ticketing

## Amazon Macie
Fully-managed data security and data privacy service that uses inventory evaluations, machine learning, and pattern matching to discover sensitive data and accessiblity in S3

Macie supports scalable on-demand and automated senstive data discovery jobs that automatically tracks changes to the bucket and only evaluates new or modified objects.

You can detect a large and growing list of senstive data types for many countries and Regions including multiple types of financial data, PHI, PII, as well as custom types

You can search, filter, and sort S3 buckets by metadata variables, such as bucket names, tags, and security controls like encryption status or public accessibility


In multi-account configuration, a single Macie Administrator account can manage all memeber accounts, includeing the creation and administration of sensitive data discovery jobs across AWS Organizations


Finding areaggregated in the Macie administrator account and sent to Amazon CloudWatch and AWS Security Hub.

You can use Macie findings with AWS Step Functions to automate remediation actions.


## Amazon Security Lake 

Centeralizes security data from AWS environments, SaaS providers, and cloud sources, into purpose-built data lake that's stored in your AWS account.

It automates the collections of security-related log and event data from integrated AWS services and third-party services.

It also helps you manage the lifecycle of data with customizable retention settings.

The data lake is baked by Amazon S3 buckets, and you retain ownership over your data.

Security Lake converts ingested data into Apache Parquet format and a standard open-source schema called the Open Cybersecurity Schema Framework (OCSF).

With OCSF support, Security Lake normalizes and combines security data from AWS and a broad range of enterprise security data sources.

## Amazon Verified Permissions

A scalable, fine-grained permissions management and authorization service for custom applications you've built

Allows dev to build secure apps faster by externalizing authorization and centralizing policy management and administration

Verified Permissions uses Cedar, an open-source policy language and SDK, to define fine-grained permissions for application users

Your authorization model is defined using principal types, resource types, and valid actions, to control who can take what actions on which resources in a given app context

Policy changes are audited so that you can see who made the changes and when.

## AWS Artifact

Go-to central resource for compliance-related information that matters to you.
It provides on-demand access to AWS security and compliance reports and select online aggreements
Reports avaliable in AWS Artifact include our Service Organization Controll (SOC) reports, Payment Card Industry (PCI) reports, and certifications from accreditation bodies across geographies and compliance verticals that validate the implementation and operating effectiveness of AWS security controls
Also includes Business Associate Addendum (BAA) and Nondisclosure Agreement (NDA)

## AWS Audit Manager

Helps continously audit your AWS usuage to simplify how you access risk and compliance with regulations and industry standards
Audit Manager automates evidence collection to resuce the "all hands on deck" manual effort that often happens for audits and enable you to scale your audit capability in the cloud as your business grows
With audit manager, it is easy to access if your policies, procedures, and activities -- also known as controls -- are operating effectively

When it's time for an audit, it helps you manage stakeholder reviews of your ontrols and enables you to build audit-ready reports with much less effort


The AWS Audit Manager prebuilt frameworks help translate evidence from cloud services into auditor-friendly reports by mapping your AWS resources to the requirements in industry standards or regulations, such as CIS AWS Foundations Benchmark, the General Data Protection Regulation (GDPR), and Payment Card Industry Data Security Standard (PCI DSS)

You can also fully customize a framework and its controls for your unique business requirements
Based on the framework you select, Audit Manager launches an assessment that continously collects and organizes relevant evidence from your AWS accounts and resources, such as resource configuration snapshots, user activity, and compliance check results

## AWS Certificate Manager

Service that lets you easily provision, manage, and deploy Secure Sockets Layer/Transport Layer Security (SSL/TLS) certificate for use with AWS services and your internal connected resources.

SSL/TLS certificates are used to secure network communications and establish the identity of websites over the Internet as well as resources on private networks

AWS Certificate Manager removes the time-consuming manual process of purchasing, uploading, and renewing SSL/TLS certificates


You can quicly request a certificate, deploy it on ACM-integrated AWS resources, such as Elastic Load Balancing, Amazon CloudFront distibutions, and APIs on API Gateway, and let AWS Certificate Manager handle certificate renewals. It also enables you to create private certificates for your internal resources and manage the certificate lifestyle centrally

Public and private certificates provisioned through AWS Certificate Manager for use with ACM-integrated services are free and you only pay for resources to run your app


You pay montly for the operation of the private certificate authority (CA) and for the private certificates you issue

## AWS CloudHSM

A cloud-based hardware security modules that enables you to easily generate and use your own encryption keys on the AWS cloud

You can manage your own encryption keys using dedicated FIPS 140-2 Level 3 validated HSMs

CloudHSM offers you the flexibility to integrate with your applications using industry-standard APIs such as PKCS#11, Java Cryptogtaphy Extenstion (JCE), and Microsoft CryptoNG (CNG) libraries


CloudHSM is standard-compliant and enables you to export all of your keys to most other commerically-avaliable HSMs, subject to your configurations. It is a fully managed service that automates time-consuming administrative tasks for you, such as hardware provisioning, software patching, high-avaliabilty, and backups
Also enables you to scale quickly by adding and removing HSM capacity on-demand, with no up-front costs

## AWS Directory Service

AWS Directory Service for Microsoft Active Directory, also known as AWS Managed Microsoft AD, enables your directory-aware workloads and AWS resources to use managed Active Directory in AWS

It is built on actual Microsoft Active Directory and does not require you to synchronize or replicate data from your existing Active Directory to the cloud

You can use Active Directory administration tools and take advantage of built-in Active Directory features such as Group Policy and Single Sign-on (SSO)

You can easily join EC2 and Amazon RDS for SQL server instances to a domain, and use AWS Enterprise IT applications such as Amazon WorkSpaces with Active Directory users and groups

## AWS Firewall Manager


