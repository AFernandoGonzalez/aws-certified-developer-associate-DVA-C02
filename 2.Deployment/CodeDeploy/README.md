# AWS CodeDeploy Cheat Sheet

## Overview
AWS CodeDeploy is a fully managed deployment service that automates software deployments to a variety of compute services such as Amazon EC2, AWS Fargate, AWS Lambda, and on-premises servers.

## Use Cases
- Automate application deployments
- Minimize downtime during deployments
- Implement continuous delivery pipelines
- Manage deployments for a variety of application types

## Key Features
- **Deployment Types**: Supports in-place and blue/green deployments.
- **Deployment Configurations**: Predefined or custom configurations that specify how deployment is executed.
- **Deployment Groups**: Groups of instances or Lambda functions targeted for deployment.
- **Revisions**: Applications, configuration files, and scripts packaged for deployment.
- **Hooks**: Lifecycle event hooks to run scripts at various stages of the deployment.

## Key Concepts

### Deployment Types
- **In-Place Deployment**: Updates the application on the same set of instances.
- **Blue/Green Deployment**: Shifts traffic from one set of instances (blue) to another (green).

### Deployment Configurations
- **OneAtATime**: Deploy to one instance at a time.
- **HalfAtATime**: Deploy to half of the instances at a time.
- **AllAtOnce**: Deploy to all instances simultaneously.
- **Custom Configurations**: Define the number or percentage of instances to be deployed simultaneously.

### Deployment Groups
- **Amazon EC2 Deployment Groups**: Groups of EC2 instances, on-premises instances, or both.
- **Amazon ECS Deployment Groups**: Groups of ECS tasks.
- **AWS Lambda Deployment Groups**: Groups of Lambda functions.

### Revisions
- **AppSpec File**: YAML or JSON file that specifies the deployment actions.
- **Source Code**: The application code to be deployed.
- **Configuration Files**: Files that configure the application.

### Hooks
- **BeforeInstall**: Run tasks before the application revision is installed.
- **AfterInstall**: Run tasks after the application revision is installed.
- **ApplicationStart**: Run tasks when the application has started.
- **ApplicationStop**: Run tasks before the application is stopped.
- **ValidateService**: Run tasks to validate the service is running.

## Security
- **IAM Roles**: Define permissions for CodeDeploy to access AWS resources.
- **Encryption**: Use AWS KMS to encrypt sensitive data.
- **VPC Integration**: Deploy applications within a VPC for additional security.

## Monitoring and Metrics
- **CloudWatch Metrics**: Monitor deployment success rates, duration, and failure rates.
- **CloudWatch Logs**: Log deployment activities for monitoring and troubleshooting.
- **Notifications**: Integrate with SNS to receive notifications on deployment status.

## Pricing
- Based on the number of instance updates performed.

## Key Terms
- **Deployment**: The process of updating the application on one or more instances or Lambda functions.
- **Deployment Group**: A set of instances, ECS tasks, or Lambda functions targeted for deployment.
- **Deployment Configuration**: Rules that specify how deployment is executed.
- **AppSpec File**: YAML or JSON file that specifies the deployment actions.
- **Hooks**: Lifecycle event hooks to run scripts at various stages of the deployment.

## Best Practices
- **Use Blue/Green Deployments**: Minimize downtime and rollback issues.
- **Monitor Deployments**: Use CloudWatch Metrics and Logs to monitor deployment performance and troubleshoot issues.
- **Secure IAM Roles**: Ensure IAM roles have the least privilege required.
- **Automate Rollbacks**: Implement automated rollback strategies for failed deployments.
- **Test Deployments**: Use a staging environment to test deployments before production.

