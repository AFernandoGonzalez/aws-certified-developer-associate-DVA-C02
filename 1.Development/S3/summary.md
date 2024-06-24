# S3 (Simple Storage Service) Cheat Sheet

## Overview
S3 is an object storage service that offers high availability, durability, and scalability.

## Use Cases
- Data backup
- Archival
- Content storage and distribution

## Key Features
- **Storage Classes**: Different access patterns.
- **Versioning**: Keep multiple versions of an object.
- **Lifecycle Policies**: Automate transition and expiration of objects.
- **Bucket Policies and ACLs**: Control access to your data.
- **Encryption**: Protect your data at rest and in transit.
- **Cross-Region Replication (CRR)**: Automatically replicate objects across buckets in different AWS regions.

## Storage Classes
| Storage Class              | Description                                 | Use Cases                                   |
|----------------------------|---------------------------------------------|---------------------------------------------|
| Standard                   | High durability, availability, and performance | Frequently accessed data                    |
| Intelligent-Tiering        | Automatic cost optimization for data with unknown access patterns | Data with unpredictable access patterns      |
| Standard-IA (Infrequent Access) | Lower cost for infrequently accessed data | Long-lived, infrequently accessed data      |
| One Zone-IA                | Lower-cost option for infrequently accessed data stored in a single availability zone | Data that can be recreated if lost          |
| Glacier                    | Low-cost archive storage with retrieval times from minutes to hours | Long-term data archiving                     |
| Glacier Deep Archive       | Lowest-cost archive storage with retrieval times up to 12 hours | Data that rarely needs to be accessed        |

## Bucket Policies and ACLs
- **Bucket Policies**: JSON-based policies to control access to buckets and objects.
- **Access Control Lists (ACLs)**: Define individual permissions on objects.

## Versioning
- Enable versioning to keep multiple versions of an object in a bucket.
- Useful for protecting against accidental deletions and overwrites.

## Lifecycle Policies
- Automate the transition of objects to different storage classes.
- Expire objects after a certain period.
- Define lifecycle rules in a JSON configuration.

## Encryption
- **Server-Side Encryption (SSE)**:
  - **SSE-S3**: Managed keys by S3.
  - **SSE-KMS**: Managed keys by AWS Key Management Service.
  - **SSE-C**: Customer-provided keys.
- **Client-Side Encryption**: Encrypt data client-side before uploading to S3.

## Data Transfer and Management
- **Multipart Upload**: Efficiently upload large objects by dividing them into smaller parts.
- **S3 Transfer Acceleration**: Faster data transfer to S3 using optimized network paths.
- **AWS Snowball**: Transfer large amounts of data using physical devices.

## Access Control
- **IAM Policies**: Control access at the user or role level.
- **Bucket Policies**: Apply policies at the bucket level.
- **ACLs**: Apply permissions at the object level.
- **Pre-Signed URLs**: Grant temporary access to objects without modifying permissions.

## Cross-Region Replication (CRR)
- Replicate objects across buckets in different AWS regions.
- Ensure data redundancy and compliance with geographic data requirements.

## Monitoring and Logging
- **S3 Access Logs**: Detailed records for requests made to your S3 bucket.
- **CloudWatch Metrics**: Monitor S3 performance metrics.
- **CloudTrail**: Track API calls made to S3.

## Common Commands
| Command                                   | Description                                              |
|-------------------------------------------|----------------------------------------------------------|
| `aws s3 ls`                               | List S3 buckets                                          |
| `aws s3 cp file.txt s3://mybucket/`       | Copy a file to an S3 bucket                              |
| `aws s3 sync localdir s3://mybucket/`     | Sync a local directory to an S3 bucket                   |
| `aws s3 mb s3://mybucket`                 | Create a new S3 bucket                                   |
| `aws s3 rb s3://mybucket --force`         | Remove an S3 bucket and its contents                     |

## Key Terms
- **Bucket**: Container for storing objects in S3.
- **Object**: Individual piece of data stored in a bucket (files, metadata).
- **Key**: Unique identifier for an object within a bucket.
- **Prefix**: Path-like structure to group objects within a bucket.

## Best Practices
- **Enable Versioning**: Protect against accidental deletions and overwrites.
- **Use Lifecycle Policies**: Optimize costs by transitioning objects to the appropriate storage class.
- **Encrypt Sensitive Data**: Use SSE or client-side encryption to protect data.
- **Monitor Access and Usage**: Use S3 access logs and CloudWatch metrics.
- **Set Up Cross-Region Replication**: Enhance data redundancy and compliance.


