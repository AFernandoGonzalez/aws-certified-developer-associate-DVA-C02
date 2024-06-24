# AWS Elastic Beanstalk Cheat Sheet

## Overview
AWS Elastic Beanstalk is a fully managed service that makes it easy to deploy, manage, and scale applications. You can simply upload your code, and Elastic Beanstalk automatically handles the deployment, from capacity provisioning, load balancing, and auto-scaling to application health monitoring.

## Use Cases
- Simplified deployment and management of applications
- Automatic scaling of applications
- Easy integration with CI/CD pipelines
- Rapid development and testing environments

## Key Features
- **Supported Platforms**: Java, .NET, Node.js, Python, Ruby, Go, Docker, and more.
- **Environment Management**: Environments, versions, and configurations.
- **Managed Environment**: Automatic management of EC2 instances, load balancers, scaling, and monitoring.
- **Customizable Environment**: Customize instance types, database configurations, and software stack.

## Key Concepts

### Application
- **Application**: The logical unit containing one or more application versions and environments.
- **Application Version**: A specific, labeled iteration of deployable code for a web application.

### Environment
- **Environment**: A version of an application deployed on AWS resources.
- **Environment Tier**: Web server environment (handles HTTP requests) or Worker environment (handles background jobs).

### Deployment Policies
- **All at Once**: Deploy the new version to all instances simultaneously.
- **Rolling**: Deploy the new version in batches.
- **Rolling with Additional Batch**: Deploy the new version in batches, but add a new batch of instances.
- **Immutable**: Deploy the new version to a new set of instances and swap them in all at once.
- **Blue/Green**: Deploy a new version to a separate environment and swap traffic.

### Configuration
- **Configuration Templates**: Define configuration settings for environments.
- **Saved Configurations**: Reusable configurations saved from a running environment.
- **Environment Variables**: Pass dynamic configuration settings to your application.

### Monitoring and Logs
- **Health Monitoring**: Monitor the health of your application and environment.
- **Logs**: Access logs from EC2 instances and other AWS resources.

## Security
- **IAM Roles**: Define permissions for Elastic Beanstalk to access AWS resources.
- **VPC Integration**: Deploy applications within a VPC for additional security.
- **Encryption**: Use SSL/TLS for secure data transmission.

## Monitoring and Metrics
- **CloudWatch Metrics**: Monitor environment health, request count, latency, and other metrics.
- **CloudWatch Alarms**: Set alarms to trigger notifications based on metrics.
- **Elastic Beanstalk Health Dashboard**: View overall health and status of your application environments.

## Pricing
- Based on the underlying AWS resources used (e.g., EC2 instances, load balancers, databases).

## Key Terms
- **Application**: A logical unit containing versions and environments.
- **Application Version**: A specific iteration of deployable code.
- **Environment**: A version of an application deployed on AWS resources.
- **Deployment Policy**: Strategy used to deploy new versions of an application.
- **Configuration Template**: Predefined settings for environments.
- **Environment Variables**: Dynamic configuration settings for applications.

## Best Practices
- **Use Environment Tiers**: Separate web and worker environments for better resource management.
- **Monitor Application Health**: Use CloudWatch Metrics and the Health Dashboard to monitor application health.
- **Automate Deployments**: Integrate Elastic Beanstalk with CI/CD pipelines for automated deployments.
- **Secure Your Environment**: Use IAM roles, VPC integration, and SSL/TLS to secure your application.
- **Use Rolling Deployments**: Minimize downtime during updates by using rolling deployments.
- **Optimize Cost**: Choose appropriate instance types and scaling policies to optimize costs.
