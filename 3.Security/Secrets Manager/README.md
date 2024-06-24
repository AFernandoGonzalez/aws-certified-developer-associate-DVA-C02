# AWS Secrets Manager Cheat Sheet

## Overview
AWS Secrets Manager helps you protect access to your applications, services, and IT resources without the upfront cost and complexity of managing your own hardware security module (HSM) infrastructure. You can rotate, manage, and retrieve database credentials, API keys, and other secrets throughout their lifecycle.

## Use Cases
- Securely manage database credentials, API keys, and other secrets
- Automatically rotate secrets without disrupting applications
- Securely retrieve secrets in your applications using AWS SDK or CLI
- Audit and monitor secret usage

## Key Features
- **Secret Rotation**: Automatically rotate secrets according to a schedule.
- **Secret Retrieval**: Securely retrieve secrets using AWS SDK, CLI, or the Secrets Manager console.
- **Secret Management**: Create, update, and delete secrets.
- **Access Control**: Control access to secrets using IAM policies.
- **Audit and Compliance**: Monitor secret usage with AWS CloudTrail and AWS Config.
- **Integration with AWS Services**: Integrates with RDS, Redshift, DocumentDB, and more for automatic secret rotation.

## Key Concepts

### Secrets
- **Secret**: Sensitive information (e.g., database credentials, API keys) that needs to be protected.
- **Secret Value**: The actual content of the secret.

### Secret Rotation
- **Automatic Rotation**: Rotate secrets on a scheduled basis without application downtime.
- **Custom Lambda Functions**: Use AWS Lambda to customize the rotation process.

### Access Control
- **IAM Policies**: Control who can create, manage, and retrieve secrets.
- **Resource-based Policies**: Attach policies directly to secrets to define access.

## Security
- **Encryption**: Secrets are encrypted at rest using AWS KMS.
- **Access Control**: Use IAM policies and resource-based policies to control access to secrets.
- **Audit and Compliance**: Track secret usage with AWS CloudTrail and ensure compliance with AWS Config rules.

## Monitoring and Metrics
- **AWS CloudTrail**: Logs all Secrets Manager API requests for auditing and compliance.
- **AWS Config**: Monitor changes to secrets and their configurations.
- **CloudWatch Metrics**: Monitor secret rotation and retrieval activities.

## Pricing
- **Secret Storage**: Charged per secret per month.
- **API Requests**: Charged per 10,000 API requests.

## Key Terms
- **Secret**: Sensitive data that needs to be securely stored and managed.
- **Secret Rotation**: The process of periodically changing a secret to enhance security.
- **IAM Policies**: Used to control access to secrets.
- **Encryption**: Protecting secrets at rest using AWS KMS.

## Best Practices
- **Enable Secret Rotation**: Automatically rotate secrets to minimize the risk of exposure.
- **Use IAM Policies**: Strictly control who can manage and retrieve secrets.
- **Audit Secret Access**: Use AWS CloudTrail to monitor and audit secret access and usage.
- **Integrate with AWS Services**: Leverage integration with RDS and other AWS services for seamless secret management.
- **Encrypt Secrets**: Ensure all secrets are encrypted using AWS KMS.
- **Limit Secret Scope**: Use resource-based policies to restrict access to specific secrets.

## Example: Creating and Retrieving a Secret

### Creating a Secret
```sh
aws secretsmanager create-secret --name MySecret --secret-string '{"username":"admin","password":"password123"}'

```

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "secretsmanager:GetSecretValue",
        "secretsmanager:PutSecretValue",
        "secretsmanager:UpdateSecretVersionStage"
      ],
      "Resource": "*"
    }
  ]
}
```

```bash
aws secretsmanager rotate-secret --secret-id MySecret --rotation-lambda-arn arn:aws:lambda:us-west-2:123456789012:function:MyRotationFunction --rotation-interval 30
```

