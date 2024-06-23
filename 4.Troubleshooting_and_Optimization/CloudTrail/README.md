# CloudWatch

## Overview
- Monitor AWS resources and applications.
- Metrics, Alarms, Logs, Events, and Dashboards.

## Common Commands

### Creating a CloudWatch Alarm
```bash
aws cloudwatch put-metric-alarm --alarm-name my-alarm --metric-name CPUUtilization --namespace AWS/EC2 --statistic Average --period 300 --threshold 80 --comparison-operator GreaterThanOrEqualToThreshold --evaluation-periods 2 --alarm-actions arn:aws:sns:us-east-1:123456789012:my-sns-topic
```

### Viewing CloudWatch Logs
```bash
aws logs describe-log-streams --log-group-name my-log-group
```

## Examples
See the [examples](./examples) folder for practical scripts and use cases.
