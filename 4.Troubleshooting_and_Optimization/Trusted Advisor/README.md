# AWS Trusted Advisor Cheat Sheet

## Overview
AWS Trusted Advisor is an online resource that helps you reduce cost, increase performance, and improve security by optimizing your AWS environment. Trusted Advisor provides real-time guidance to help you provision your resources following AWS best practices.

## Use Cases
- **Cost Optimization**: Identify opportunities to reduce your AWS bill.
- **Performance**: Improve the performance of your AWS applications.
- **Security**: Enhance the security of your AWS resources.
- **Fault Tolerance**: Increase the reliability of your AWS environment.
- **Service Limits**: Monitor your AWS usage to ensure you stay within service limits.

## Key Features
- **Checks and Recommendations**: Provides a variety of checks across multiple categories to help you optimize your AWS environment.
- **Dashboard**: Centralized view of all checks with actionable recommendations.
- **Weekly Email Notifications**: Summarizes check statuses and recommended actions.
- **Integration with AWS Support**: Available to AWS Basic, Developer, Business, and Enterprise Support customers.
- **Automated Actions**: Use AWS Lambda to automate responses to Trusted Advisor alerts.

## Key Concepts

### Categories of Checks
- **Cost Optimization**: Identifies idle and underutilized resources.
- **Performance**: Recommends improvements to enhance the performance of your resources.
- **Security**: Detects security vulnerabilities and compliance issues.
- **Fault Tolerance**: Advises on how to build a more resilient infrastructure.
- **Service Limits**: Alerts you when you approach service limits.

### Example Checks
- **Cost Optimization**: Low Utilization Amazon EC2 Instances, Underutilized Amazon EBS Volumes.
- **Performance**: High Utilization Amazon EC2 Instances, CloudFront Content Delivery Optimization.
- **Security**: IAM Use, MFA on Root Account, S3 Bucket Permissions.
- **Fault Tolerance**: Amazon RDS Backups, Amazon S3 Bucket Versioning.
- **Service Limits**: Checks for service usage against limits.

## Security
- **IAM Policies**: Use IAM policies to control access to Trusted Advisor.
- **Automated Responses**: Implement automated responses to alerts using AWS Lambda.

## Pricing
- **Basic and Developer Support Plans**: Access to a limited number of Trusted Advisor checks.
- **Business and Enterprise Support Plans**: Access to all Trusted Advisor checks.

## Key Terms
- **Check**: A specific test performed by Trusted Advisor to evaluate your AWS environment.
- **Recommendation**: Actionable advice provided based on the results of a check.
- **Dashboard**: The interface that displays the results of all Trusted Advisor checks.

## Best Practices
- **Regular Review**: Regularly review Trusted Advisor recommendations to keep your AWS environment optimized.
- **Automate Responses**: Use AWS Lambda to automate responses to Trusted Advisor alerts.
- **Integrate with Monitoring Tools**: Combine Trusted Advisor with other AWS monitoring tools like CloudWatch for comprehensive insights.

## Example: Setting Up Trusted Advisor

### Step 1: Access Trusted Advisor
1. Sign in to the AWS Management Console.
2. Navigate to the Trusted Advisor console.

### Step 2: View the Dashboard
1. The dashboard displays the results of all checks.
2. Each check is categorized into cost optimization, performance, security, fault tolerance, and service limits.

### Step 3: Review and Act on Recommendations
1. Click on a category to view detailed recommendations.
2. Follow the provided advice to optimize your AWS environment.

### Step 4: Set Up Email Notifications
1. In the Trusted Advisor console, navigate to the "Preferences" section.
2. Enable weekly email notifications to stay informed about check statuses and recommendations.

## Example Checks and Recommendations

### Cost Optimization: Low Utilization Amazon EC2 Instances
- **Check**: Identifies EC2 instances with low utilization.
- **Recommendation**: Stop or downsize underutilized instances to save costs.

### Performance: High Utilization Amazon EC2 Instances
- **Check**: Detects EC2 instances with high utilization that may impact performance.
- **Recommendation**: Consider resizing or adding instances to balance the load.

### Security: IAM Use
- **Check**: Verifies that AWS Identity and Access Management (IAM) is being used to control access.
- **Recommendation**: Implement IAM roles and policies to enforce least privilege access.

### Fault Tolerance: Amazon RDS Backups
- **Check**: Ensures that RDS instances have automated backups enabled.
- **Recommendation**: Enable automated backups to protect your databases against data loss.

### Service Limits: Usage Check
- **Check**: Monitors your usage against AWS service limits.
- **Recommendation**: Request a limit increase if you are approaching the service limit.

