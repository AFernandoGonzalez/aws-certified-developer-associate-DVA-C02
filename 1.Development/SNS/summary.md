# Amazon SNS Cheat Sheet

## Overview
Amazon Simple Notification Service (SNS) is a fully managed messaging service for both application-to-application (A2A) and application-to-person (A2P) communication.

## Use Cases
- Send notifications to mobile devices, email, and other endpoints
- Decouple microservices, distributed systems, and serverless applications
- Broadcast messages to multiple subscribers
- Trigger Lambda functions, HTTP endpoints, or other AWS services

## Key Features
- **Message Delivery**: Supports multiple protocols including HTTP/S, email, SMS, Lambda, and SQS.
- **Scalability**: Automatically scales to handle large volumes of messages.
- **Fan-Out**: Messages can be sent to multiple endpoints (subscribers).
- **Message Filtering**: Filter messages sent to subscribers.
- **Security**: Integration with IAM, VPC endpoints, and encryption.

## Key Concepts

### Topics
- **Topic**: An access point for allowing recipients to dynamically subscribe for identical copies of the same notification.
- **Subscribers**: Endpoints that receive messages from a topic.

### Subscriptions
- **Protocol**: The delivery method for messages (e.g., HTTP/S, email, SMS, Lambda, SQS).

### Messages
- **Message Attributes**: Additional metadata about the message.
- **Message Structure**: Can send different messages to different protocols using a single publish action.

## Security
- **IAM Policies**: Fine-grained access control for SNS topics.
- **Encryption**: Server-side encryption using AWS KMS.
- **VPC Endpoints**: Securely connect to SNS within your VPC.

## Monitoring and Metrics
- **CloudWatch Metrics**: Monitor number of messages published, delivered, and failed.
- **CloudWatch Logs**: Log data from SNS for monitoring and troubleshooting.

## Pricing
- Based on the number of requests, notifications delivered, and data transfer.

## Common Commands
| Command                                      | Description                                     |
|----------------------------------------------|-------------------------------------------------|
| `aws sns create-topic`                       | Create a new SNS topic                          |
| `aws sns list-topics`                        | List all SNS topics                             |
| `aws sns subscribe`                          | Subscribe an endpoint to an SNS topic           |
| `aws sns publish`                            | Publish a message to an SNS topic               |
| `aws sns list-subscriptions-by-topic`        | List subscriptions for a specific topic         |
| `aws sns delete-topic`                       | Delete an SNS topic                             |
| `aws sns set-topic-attributes`               | Set attributes for an SNS topic                 |
| `aws sns get-topic-attributes`               | Retrieve attributes of an SNS topic             |

## Key Terms
- **Topic**: A communication channel for sending messages.
- **Subscription**: The association between a topic and an endpoint.
- **Message**: The content sent to a topic and delivered to subscribers.
- **Message Attribute**: Metadata about the message.

## Best Practices
- **Use Topics for Decoupling**: Decouple microservices and distributed systems.
- **Implement Message Filtering**: Reduce the amount of unnecessary data sent to subscribers.
- **Monitor Metrics**: Use CloudWatch to monitor message delivery and failure rates.
- **Secure Your Topics**: Use IAM policies and encryption.
- **Use Dead-Letter Queues**: Handle undelivered messages.

## Example: Creating an SNS Topic
```bash
aws sns create-topic \
    --name my-topic

aws sns list-topics


aws sns subscribe \
    --topic-arn arn:aws:sns:us-east-1:123456789012:my-topic \
    --protocol email \
    --notification-endpoint user@example.com


aws sns publish \
    --topic-arn arn:aws:sns:us-east-1:123456789012:my-topic \
    --message "This is a test message"


aws sns publish \
    --topic-arn arn:aws:sns:us-east-1:123456789012:my-topic \
    --message "This is a test message with attributes" \
    --message-attributes '{"Title":{"DataType":"String","StringValue":"MyTitle"}}'


aws sns set-topic-attributes \
    --topic-arn arn:aws:sns:us-east-1:123456789012:my-topic \
    --attribute-name DisplayName \
    --attribute-value "My Topic Display Name"


aws sns get-topic-attributes \
    --topic-arn arn:aws:sns:us-east-1:123456789012:my-topic


aws sns delete-topic \
    --topic-arn arn:aws:sns:us-east-1:123456789012:my-topic
