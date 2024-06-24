# AWS WAF Cheat Sheet

## Overview
AWS WAF (Web Application Firewall) helps protect your web applications from common web exploits that could affect application availability, compromise security, or consume excessive resources. It allows you to control how traffic reaches your applications by defining customizable web security rules.

## Use Cases
- Protect web applications from common threats such as SQL injection and cross-site scripting (XSS)
- Control access to your applications based on conditions such as IP addresses, HTTP headers, HTTP body, or URI strings
- Rate-limit requests to your applications to mitigate DDoS attacks
- Integrate with AWS services like Amazon CloudFront, Application Load Balancer (ALB), and API Gateway

## Key Features
- **Customizable Rules**: Define your own rules to filter web traffic.
- **Managed Rules**: Use pre-configured rules from AWS and AWS Marketplace sellers.
- **Web ACLs (Access Control Lists)**: Collections of rules that you apply to your AWS resources.
- **Bot Control**: Protect applications from common and automated bots.
- **Rate-Based Rules**: Automatically block requests from IP addresses that make too many requests in a specified time period.
- **Logging and Monitoring**: Monitor traffic and configure real-time alerts.

## Key Concepts

### Web ACL (Access Control List)
- **Web ACL**: A set of rules that define the web requests to allow, block, or count.
- **Association**: Apply Web ACLs to CloudFront distributions, ALBs, and API Gateways.

### Rules
- **Rule**: A condition-based rule that determines whether to allow, block, or count requests.
- **Managed Rules**: Pre-configured rules managed by AWS or third parties.
- **Custom Rules**: User-defined rules based on specific conditions.

### Conditions
- **IP Match Condition**: Filter traffic based on IP addresses.
- **String Match Condition**: Filter traffic based on string matches in the request.
- **SQL Injection Match Condition**: Detect SQL injection attacks.
- **XSS Match Condition**: Detect cross-site scripting attacks.
- **Geo Match Condition**: Filter requests based on the geographical location.

### Rate-Based Rules
- **Rate-Based Rule**: Blocks requests from an IP address that exceed a specified rate limit.

## Security
- **Integration with AWS Shield**: Enhanced DDoS protection when used with AWS Shield Advanced.
- **Logging**: Configure logging to send detailed information about web requests to Amazon Kinesis Data Firehose, Amazon S3, or Amazon CloudWatch Logs.

## Monitoring and Metrics
- **AWS CloudWatch**: Monitor metrics and create alarms for WAF.
- **AWS CloudTrail**: Track API calls and access logs.
- **AWS WAF Logs**: Log requests for detailed visibility into traffic.

## Pricing
- **Web ACLs**: Charged per Web ACL.
- **Rules**: Charged per rule.
- **Requests**: Charged per 1 million requests.

## Key Terms
- **Web ACL**: A set of rules to filter web traffic.
- **Rule**: A condition to allow, block, or count requests.
- **Managed Rules**: Pre-configured rulesets.
- **Rate-Based Rule**: A rule that limits the rate of requests.

## Best Practices
- **Use Managed Rules**: Quickly protect your applications with pre-configured rules.
- **Implement Custom Rules**: Tailor rules to your specific application needs.
- **Enable Logging**: Log requests to analyze traffic and fine-tune rules.
- **Monitor Metrics**: Use CloudWatch to monitor WAF metrics and set up alerts.
- **Integrate with AWS Shield**: Enhance protection against DDoS attacks.

## Example: Creating a Web ACL

### Step 1: Create a Web ACL
1. Sign in to the AWS Management Console.
2. Navigate to the AWS WAF console.
3. Choose "Create web ACL."
4. Enter a name and select the AWS resource to associate with the Web ACL (e.g., CloudFront distribution).

### Step 2: Add Rules to the Web ACL
1. Choose "Add rules."
2. Select either "Add managed rule groups" or "Add my own rules and rule groups."
3. Configure the rule conditions (e.g., IP match, string match, SQL injection match).
4. Define the action for each rule (allow, block, count).

### Step 3: Review and Create
1. Review the Web ACL configuration.
2. Choose "Create web ACL" to apply the rules to the selected resource.

## Example: Rate-Based Rule

### Step 1: Create a Rate-Based Rule
1. Navigate to the AWS WAF console.
2. Choose "Create rule."
3. Enter a name for the rule.
4. Select "Rate-based rule."
5. Set the rate limit (e.g., 2000 requests per 5 minutes).

### Step 2: Add Conditions to the Rule
1. Add conditions such as IP match or string match if needed.
2. Define the action (block, allow, count).

### Step 3: Add the Rule to a Web ACL
1. Edit the Web ACL.
2. Add the rate-based rule to the Web ACL.
3. Save the changes.
