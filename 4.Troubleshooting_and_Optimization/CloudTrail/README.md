# AWS CloudTrail Cheat Sheet

## Overview
AWS CloudTrail is a service that enables governance, compliance, operational auditing, and risk auditing of your AWS account. With CloudTrail, you can log, continuously monitor, and retain account activity related to actions across your AWS infrastructure.

## Use Cases
- **Security Analysis**: Track user activity and API usage.
- **Compliance Auditing**: Ensure compliance with internal policies and regulatory standards.
- **Resource Change Tracking**: Monitor changes to AWS resources.
- **Operational Troubleshooting**: Investigate operational issues and track changes.

## Key Features
- **Event History**: View, search, and download the past 90 days of account activity.
- **Management Events**: Log management operations performed on resources in your AWS account.
- **Data Events**: Log data operations performed on or within a resource (e.g., S3 object-level operations).
- **Insights**: Detect unusual activity in your account.
- **Multiple Trails**: Create multiple trails to deliver log files to separate S3 buckets and log different events.
- **Integration with CloudWatch Logs**: Monitor and receive alerts on specific API activity.

## Key Concepts

### Trails
- **Trail**: A configuration that enables delivery of events as log files to an S3 bucket.
- **Multi-Region Trail**: A trail that logs events from all regions in your account.
- **Single-Region Trail**: A trail that logs events from one region in your account.
- **Global Service Events**: Events that are recorded regardless of the region (e.g., IAM operations).

### Event Types
- **Management Events**: Operations that manage AWS resources (e.g., creating an EC2 instance, deleting an S3 bucket).
- **Data Events**: Operations that affect the data in your resources (e.g., S3 object-level actions, Lambda function invocations).
- **Insight Events**: Detect unusual activity (e.g., spikes in resource provisioning).

### Logs and Storage
- **S3 Bucket**: Primary storage for CloudTrail logs.
- **CloudWatch Logs**: Optional storage for real-time monitoring and alerting.

## Security
- **Encryption**: Logs can be encrypted using AWS KMS.
- **Access Control**: Use IAM policies to control access to CloudTrail and log files.
- **Log Integrity**: Enable log file validation to detect whether log files were modified or deleted.

## Monitoring and Metrics
- **AWS CloudWatch Logs**: Stream CloudTrail logs to CloudWatch for real-time monitoring and alerting.
- **AWS CloudWatch Events**: Create rules to respond to specific CloudTrail events.
- **CloudTrail Insights**: Detect and analyze unusual operational activity.

## Pricing
- **Trail Creation**: No additional charge.
- **Management Events**: Recorded at no additional charge.
- **Data Events**: Charged per 100,000 events.
- **CloudTrail Insights**: Charged per insight event.

## Key Terms
- **Trail**: Configuration to log AWS API calls and events.
- **Management Events**: Logs related to resource management.
- **Data Events**: Logs related to resource data operations.
- **Insight Events**: Logs related to unusual activity.

## Best Practices
- **Enable Multi-Region Trails**: Ensure all regions are covered.
- **Enable CloudTrail Insights**: Detect and investigate unusual activity.
- **Stream to CloudWatch Logs**: For real-time monitoring and alerting.
- **Encrypt Logs**: Use AWS KMS to encrypt logs.
- **Implement IAM Policies**: Restrict access to CloudTrail and S3 bucket.

## Example: Creating a Trail

### Step 1: Create a Trail
1. Sign in to the AWS Management Console.
2. Navigate to the AWS CloudTrail console.
3. Choose "Create trail."
4. Enter a name for the trail.
5. Choose the "Apply trail to all regions" option to log events from all regions.

### Step 2: Configure the Trail
1. Specify an S3 bucket to store the logs.
2. Enable encryption using AWS KMS (optional).
3. Configure CloudWatch Logs integration (optional).
4. Enable CloudTrail Insights (optional).

### Step 3: Review and Create
1. Review the trail configuration.
2. Choose "Create trail" to finalize the setup.

## Example: Monitoring CloudTrail Logs with CloudWatch Logs

### Step 1: Create a CloudWatch Logs Group
1. Navigate to the CloudWatch console.
2. Choose "Logs" and then "Create log group."
3. Enter a name for the log group.

### Step 2: Configure CloudTrail to Send Logs to CloudWatch
1. Navigate to the CloudTrail console.
2. Choose the trail you want to configure.
3. Under "CloudWatch Logs," choose "Configure."
4. Select the log group created in step 1.
5. Choose or create an IAM role that CloudTrail can assume to write to CloudWatch Logs.

### Step 3: Create Alarms for Specific Events
1. In the CloudWatch console, navigate to "Alarms" and choose "Create Alarm."
2. Select the metric and conditions you want to monitor (e.g., specific API calls).
3. Configure the alarm actions (e.g., send an SNS notification).
4. Review and create the alarm.

