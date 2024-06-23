# IAM (Identity and Access Management)

## Overview
- Manage users, groups, roles, and permissions.
- MFA (Multi-Factor Authentication).

## Common Commands

### Creating an IAM User
```bash
aws iam create-user --user-name my-user
```

### Attaching a Policy to a User
```bash
aws iam attach-user-policy --user-name my-user --policy-arn arn:aws:iam::aws:policy/AmazonS3FullAccess
```

## Examples
See the [examples](./examples) folder for practical scripts and use cases.
