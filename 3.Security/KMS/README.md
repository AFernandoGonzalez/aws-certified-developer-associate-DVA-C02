# AWS KMS Cheat Sheet

## Overview
AWS Key Management Service (KMS) is a managed service that makes it easy to create and control cryptographic keys used to encrypt your data. KMS integrates with other AWS services to help protect your data at rest and in transit.

## Use Cases
- Encrypt data in AWS services such as S3, EBS, and RDS
- Manage encryption keys for your applications
- Control access to encryption keys using IAM policies
- Implement data encryption in compliance with regulatory requirements

## Key Features
- **Customer Master Keys (CMKs)**: Master keys used to generate, encrypt, and decrypt data keys.
- **Data Keys**: Keys used to encrypt data. Generated and encrypted by CMKs.
- **Key Policies**: Define permissions for using and managing CMKs.
- **Key Rotation**: Automatically rotate CMKs to enhance security.
- **Audit and Compliance**: Track key usage and management activities using AWS CloudTrail.
- **Integration with AWS Services**: Seamlessly integrates with S3, EBS, RDS, Lambda, and more.

## Key Concepts

### Customer Master Keys (CMKs)
- **Symmetric CMKs**: Use a single encryption key for both encryption and decryption.
- **Asymmetric CMKs**: Use a key pair (public and private) for encryption and decryption.
- **Managed CMKs**: AWS-managed keys for AWS services.
- **Customer Managed CMKs**: Customer-created and managed keys.

### Data Keys
- **Encryption Data Keys**: Used to encrypt data.
- **Data Key Pairs**: Used in asymmetric cryptographic operations.

### Key Policies
- **Key Policy**: A document that defines permissions for using and managing a CMK.
- **IAM Policies**: Complement key policies to control access to CMKs.
- **Grants**: Provide temporary permissions to use CMKs.

### Key Rotation
- **Automatic Key Rotation**: AWS KMS can automatically rotate CMKs annually.
- **Manual Key Rotation**: Customers can manually rotate keys by creating new CMKs and updating applications.

## Security
- **Access Control**: Use IAM policies and key policies to control access to CMKs.
- **Encryption Algorithms**: Supports various algorithms for encryption, decryption, signing, and verification.
- **FIPS 140-2**: AWS KMS is validated for compliance with FIPS 140-2.

## Monitoring and Metrics
- **AWS CloudTrail**: Logs all KMS API requests for auditing and compliance.
- **CloudWatch Metrics**: Monitor the usage of KMS keys and set alarms.

## Pricing
- Based on the number of keys and the number of requests made to KMS.
- **Key Storage**: Charged per CMK per month.
- **Request Charges**: Charged per cryptographic request.

## Key Terms
- **CMK (Customer Master Key)**: A master key used to encrypt and decrypt data keys.
- **Data Key**: A key used to encrypt data, generated and managed by CMKs.
- **Key Policy**: A document defining permissions for a CMK.
- **Key Rotation**: The process of periodically changing cryptographic keys to enhance security.
- **Grant**: A mechanism to provide temporary permissions to a CMK.

## Best Practices
- **Use CMKs for Sensitive Data**: Encrypt sensitive data using CMKs.
- **Implement Key Rotation**: Enable automatic key rotation for better security.
- **Audit Key Usage**: Use AWS CloudTrail to monitor and audit key usage.
- **Control Access**: Use IAM policies and key policies to restrict access to CMKs.
- **Integrate with AWS Services**: Leverage KMS integration with other AWS services for seamless encryption.
- **Encrypt Data in Transit and at Rest**: Ensure data is encrypted both in transit and at rest.
