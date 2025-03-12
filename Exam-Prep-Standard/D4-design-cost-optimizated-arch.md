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

## Design Cost-Optimized Compute Solutions

## Design Cost-Optimized Network Architectures

