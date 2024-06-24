# AWS IAM Cheat Sheet

## Overview
AWS Identity and Access Management (IAM) enables you to securely manage access to AWS services and resources. Using IAM, you can create and manage AWS users and groups, and use permissions to allow and deny their access to AWS resources.

## Use Cases
- Securely manage access to AWS services and resources
- Implement the principle of least privilege
- Manage user identities and permissions
- Use roles to delegate access

## Key Features
- **Users**: Individual accounts with specific permissions.
- **Groups**: Collections of users with shared permissions.
- **Roles**: Grant temporary access to AWS resources.
- **Policies**: Documents that define permissions.
- **Federation**: Allow external identities to access AWS resources.
- **Multi-Factor Authentication (MFA)**: Enhance security for IAM users.

## Key Concepts

### Users
- **User**: An individual identity with long-term credentials.
- **Permissions**: Defined by attaching policies to users.

### Groups
- **Group**: A collection of users managed as a single entity.
- **Group Policies**: Attach policies to groups to manage permissions for all members.

### Roles
- **Role**: An identity with permissions to perform specific actions.
- **Assume Role**: Users or services can assume a role to gain its permissions.
- **Temporary Security Credentials**: Roles provide short-term access.

### Policies
- **Policy**: A JSON document that defines permissions.
- **Managed Policies**: AWS-managed or customer-managed policies.
- **Inline Policies**: Policies embedded directly within a user, group, or role.

### Federation
- **Identity Federation**: Allow external identities to access AWS resources.
- **SAML Federation**: Integrate with SAML 2.0 identity providers.
- **Web Identity Federation**: Use Amazon, Facebook, Google, etc., for authentication.

### Security
- **MFA**: Add an extra layer of security using hardware or virtual devices.
- **IAM Access Analyzer**: Identify resources that are shared with external entities.
- **Password Policies**: Enforce password complexity and rotation requirements.

## Monitoring and Metrics
- **AWS CloudTrail**: Track user activity and API usage.
- **AWS Config**: Monitor configuration changes and compliance.
- **IAM Access Advisor**: View service permissions granted to a user and when they were last accessed.

## Pricing
- IAM is free of charge. You only pay for the AWS resources you use.

## Key Terms
- **User**: An individual identity with specific permissions.
- **Group**: A collection of users with shared permissions.
- **Role**: An identity that can be assumed by users or services for temporary access.
- **Policy**: A document that defines permissions for users, groups, or roles.
- **MFA**: Multi-Factor Authentication for enhanced security.
- **Federation**: Allow external identities to access AWS resources.

## Best Practices
- **Follow the Principle of Least Privilege**: Grant only the permissions necessary for users to perform their tasks.
- **Enable MFA**: Add an extra layer of security for sensitive operations.
- **Use Roles for Applications**: Grant permissions to applications using roles rather than long-term credentials.
- **Regularly Review Policies**: Audit and review IAM policies and permissions regularly.
- **Use IAM Access Analyzer**: Identify and mitigate overly permissive access.
- **Enable CloudTrail**: Track and monitor IAM actions for security and compliance.

