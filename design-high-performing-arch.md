# design-high-performing-arch.md

## Determine high-performing and elastic compute solutions

Four layers

- Compute
  
- Storage
  
- Database
  
- Network

### Storage forms

- Block (EBS)
  
- Object (S3)

- File (EFS)

Learn scaling for each, i.e. EBS scales differently than others because you scale the volume (volume type, size, and IOPS capacity)

EBS scaling is manual but supports live configuration changes when in prod

EFS scaling vertically is done automatcially as you add and remove files (Least amount of operational work)

### File storage to know

AWS Storage Gateway- Help you move files to EFS from on-premises for hybrid storage solutions

Amazon FSx - File server similar to EFS but for Linux and for hybrid solutions too
It is a fully-managed Windows file system share drive, supports SMB and NTFS, and supports AD integration 

EFS is great for large repositories, development enivornment, media storage, and more

#### Key words for EFS

- network-based file systems
- NFS
- Hybrid Access (VPN or Direct Connect)
- Linux instances

Configuration of EFS for performance - General Purpose and Max IO 

#### Cost optimization lifestyle policies

Data isn't static, once you operate your applications over time the rate of data accumilation should be considered when making arch decisions ( 1 TB this year 10 T next year



### Object storage to know

- S3 storage classes
- Basic API calls
- Multi-part uploads

S3 is good for large data storage and backup/recovery 

Understand scalability, avaliabilty, durability, security, performance, and cost optimization with S3

S3 is global service and ran in every AWS Region

Your S3 data is stored in a region and is replicated for Avaliabilty Zone fault tolerance and can be replicated in another region

For data upload or transfers, you can improve the performance in S3 with S3 Accelerator for more performant uploads and caching with Cloufront

### Block Storage to know

Know EBS volume types their performance, use cases, and IOPS 

EBS volumes are extermely low latency and the performance is configurable

EC2 has two storage: instant store (local store and ephemeral) and EBS volumes (persistant storage) 

EBS snapshots for EBS for backup and disaster recovery and stored in S3 and becomes region resilient 

#### Key words for EBS:

- DAS
- SAN 
- Perisistant Storage for EC2 

## Design high-preforming and elastic compute solutions


