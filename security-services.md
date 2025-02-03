Amazon Cognito
Lets users sign in with facebook and other SAML 2.0 to your web and mobile app

Amazon Detective
Investigates root causes of potential security issues or suspicious activities of current and future accounts
Using AWS security services such as GuardDuty, Macie, and Security hub can be used to identify security issues but not complex and deep investigations like Dectective
Uses VPC flow logs, AWS CloudTrail, and Amazon GuardDuty as data sources to create visualization of details to drill down to the root cause

Amazon GuardDuty
Threat detection that continously monitors for bad activity and weird behavior to protect AWS accounts, workloads, Kubernetes clusters, and S3 data
Looks at unusual API calls, unauthorized deployments, and exfilterated credentials to indicate compromise.
Works with AWS Organizations for organizaion-wide analyzing of account events for signs of unauthorized use
Uses threat feeds and machine learning anomaly detection to detect anomalies in account and workload activity
It sends detailed findings to GuardDuty, CloudWatch Events, and security hub. Further investigation is done by Dectective

Amazon Inspector
Automated vulnerability management service that continously scans AWS workkloads for software vulnerabilities and unintended network exposure
Uses across all accounts once allowed and automatically discovers running EC2 instance and container images in ECR and scans for vulnerabilities
A risk score using CVE information with factors such as network access and exploitability to prioritize the most critical vulnerabilities
Inspector uses SSM agent to eliminate the need for you to deploy a standalone agent for EC2 instance assessments.
Inspector is also integrated with ECR to support intelligent, cost-efficient, and continual vulnerability assessments of container images\
All findings are aggregated into the Amazon Inspector Console, routed to AWS Security Hub, and pushed through Amazon EventBridge to automate workflows such as ticketing

Amazon Macie
Fully-managed data security and data privacy service that uses inventory evaluations, machine learning, and pattern matching to discover sensitive data and accessiblity in S3
Macie supports scalable on-demand and automated senstive data discovery jobs that automatically tracks changes to the bucket and only evaluates new or modified objects.
You can detect a large and growing list of senstive data types for many countries and Regions including multiple types of financial data, PHI, PII, as well as custom types
You can search, filter, and sort S3 buckets by metadata variables, such as bucket names, tags, and security controls like encryption status or public accessibility..
In multi-account configuration, a single Macie Administrator account can manage all memeber accounts, includeing the creation and administration of sensitive data discovery jobs across AWS Organizations
Finding areaggregated in the Macie administrator account and sent to Amazon CloudWatch and AWS Security Hub.
You can use Macie findings with AWS Step Functions to automate remediation actions.


Amazon Security Lake 
Centeralizes security data from AWS environments, SaaS providers, and cloud sources, into purpose-built data lake that's stored in your AWS account.
It automates the collections of security-related log and event data from integrated AWS services and third-party services.
It also helps you manage the lifecycle of data with customizable retention settings.
The data lake is baked by Amazon S3 buckets, and you retain ownership over your data.
Security Lake converts ingested data into Apache Parquet format and a standard open-source schema called the Open Cybersecurity Schema Framework (OCSF).
With OCSF support, Security Lake normalizes and combines security data from AWS and a broad range of enterprise security data sources.

Amazon Verified Permissions
A scalable, fine-grained permissions management and authorization service for custom applications you've built
Allows dev to build secure apps faster by externalizing authorization and centralizing policy 

