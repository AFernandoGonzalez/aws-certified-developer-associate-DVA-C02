# AWS CloudWatch Cheat Sheet

## Overview
Amazon CloudWatch is a monitoring and management service that provides data and actionable insights for AWS, hybrid, and on-premises applications and infrastructure resources. It allows you to collect and track metrics, collect and monitor log files, and set alarms.

## Use Cases
- Monitoring AWS resources such as EC2, DynamoDB, RDS, and more.
- Setting alarms to respond to changes in your AWS resources.
- Collecting and analyzing log files.
- Visualizing metrics and logs to gain operational insights.
- Automating responses to changes in your applications.

## Key Features
- **Metrics**: Collect and track metrics from AWS services and custom sources.
- **Alarms**: Set thresholds on metrics and receive notifications or trigger actions.
- **Logs**: Collect, monitor, and analyze log data from AWS resources and custom sources.
- **Dashboards**: Create customizable dashboards to visualize metrics and logs.
- **Events**: Respond to changes in your AWS environment in real-time.

## Key Concepts

### Metrics
- **Namespace**: A container for CloudWatch metrics. AWS services have their own namespaces.
- **Metric**: A time-ordered set of data points published to CloudWatch.
- **Dimension**: A name/value pair that uniquely identifies a metric.
- **Statistics**: Aggregations of metric data over specified periods (e.g., average, sum, minimum, maximum).
- **Periods**: The length of time associated with a specific CloudWatch statistic.

### Alarms
- **Alarm**: Monitors a single metric or the result of a math expression based on multiple metrics.
- **Threshold**: A value that triggers the alarm when crossed.
- **Actions**: Responses triggered by an alarm state change (e.g., send an SNS notification, trigger an Auto Scaling policy).

### Logs
- **Log Groups**: Groups of log streams that share the same retention, monitoring, and access control settings.
- **Log Streams**: Sequences of log events from the same source.
- **Log Events**: Records of activity from various sources.
- **Metric Filters**: Extract metric data from log events.

### Dashboards
- **Dashboard**: A customizable home page in the CloudWatch console that can display metrics, alarms, and logs.

### Events
- **Event**: A change in an AWS environment.
- **Rule**: Matches incoming events and routes them to targets for processing.

## Monitoring and Metrics
- **CloudWatch Metrics**: Collect and visualize metrics from AWS services and custom applications.
- **CloudWatch Alarms**: Create alarms to monitor metrics and respond to changes.
- **CloudWatch Logs**: Collect, store, and analyze log data from AWS resources and applications.
- **CloudWatch Dashboards**: Create dashboards to visualize and track key metrics and logs.
- **CloudWatch Events**: Set rules to automate responses to changes in your AWS environment.

## Security
- **IAM Policies**: Control access to CloudWatch resources using IAM policies.
- **Encryption**: Encrypt log data using AWS KMS.
- **Log Data Retention**: Configure retention settings for log data.

## Pricing
- **Metrics**: Charged per metric per month.
- **Alarms**: Charged per alarm per month.
- **Logs**: Charged per log group, log ingestion, and log storage.
- **Dashboards**: Charged per dashboard per month.
- **Events**: Charged per event rule invocation.

## Key Terms
- **Metric**: Data point tracked over time.
- **Alarm**: Monitors metrics and triggers actions.
- **Log Group**: Collection of log streams.
- **Dashboard**: Visual display of metrics and logs.
- **Event**: Change in the AWS environment.

## Best Practices
- **Use Detailed Monitoring**: Enable detailed monitoring for more granular metrics.
- **Create Alarms**: Set up alarms to proactively respond to changes.
- **Enable Log Retention**: Configure log retention settings based on your requirements.
- **Use Dashboards**: Create dashboards to monitor key metrics and logs.
- **Automate with Events**: Use CloudWatch Events to automate responses to changes.

## Example: Creating a CloudWatch Alarm

### Step 1: Create an Alarm
1. Sign in to the AWS Management Console.
2. Navigate to the CloudWatch console.
3. Choose "Alarms" and then "Create Alarm."
4. Select the metric you want to monitor.

### Step 2: Configure the Alarm
1. Define the threshold for the alarm.
2. Set the period and evaluation periods.
3. Choose the actions to take when the alarm state changes (e.g., send an SNS notification).

### Step 3: Review and Create
1. Review the alarm configuration.
2. Choose "Create alarm" to finalize the setup.

## Example: Creating a CloudWatch Dashboard

### Step 1: Create a Dashboard
1. Sign in to the AWS Management Console.
2. Navigate to the CloudWatch console.
3. Choose "Dashboards" and then "Create dashboard."
4. Enter a name for the dashboard.

### Step 2: Add Widgets to the Dashboard
1. Choose "Add widget."
2. Select the type of widget (e.g., Line, Stack, Number).
3. Configure the widget to display the desired metrics or logs.
4. Repeat to add more widgets as needed.

### Step 3: Review and Save
1. Arrange the widgets on the dashboard.
2. Choose "Save dashboard" to finalize the setup.

