# Amazon SQS Cheat Sheet

## Overview
Amazon Simple Queue Service (SQS) is a fully managed message queuing service that enables you to decouple and scale microservices, distributed systems, and serverless applications.

## Use Cases
- Decouple components of a distributed application
- Buffer and batch tasks
- Handle asynchronous processing
- Build fault-tolerant applications

## Key Features
- **Message Queues**: Standard and FIFO queues
- **Scalability**: Automatically scales to handle large volumes of messages
- **Reliability**: Ensures messages are delivered at least once
- **Message Retention**: Configurable retention period
- **Security**: IAM integration, message encryption, and VPC endpoints

## Queue Types

### Standard Queues
- **Unlimited Throughput**: Nearly unlimited number of transactions per second.
- **At-Least-Once Delivery**: Messages are delivered at least once, but occasionally more than once.
- **Best-Effort Ordering**: Messages might not be received in the order they were sent.

### FIFO Queues
- **Ordered Delivery**: Messages are delivered in the exact order they are sent.
- **Exactly-Once Processing**: Each message is processed exactly once.
- **Limited Throughput**: Supports up to 300 messages per second (can be increased with batching).

## Key Concepts

### Messages
- **Message Size**: Maximum of 256 KB.
- **Message Attributes**: Key-value pairs that provide additional information about the message.

### Visibility Timeout
- The period during which a message is invisible to other consumers after being retrieved.

### Delay Queues
- Messages are hidden for a specified duration after being sent to the queue.

### Dead-Letter Queues (DLQ)
- Queues that store messages that were not successfully processed after a specified number of attempts.

## Security
- **IAM Policies**: Fine-grained access control for queues.
- **Encryption**: Server-side encryption using AWS KMS.
- **VPC Endpoints**: Securely connect to SQS within your VPC.

## Monitoring and Metrics
- **CloudWatch Metrics**: Monitor queue length, message size, and other metrics.
- **CloudWatch Logs**: Log data from SQS for monitoring and troubleshooting.

## Pricing
- Based on the number of requests (Send, Receive, Delete) and data transfer.

## Common Commands
| Command                                      | Description                                  |
|----------------------------------------------|----------------------------------------------|
| `aws sqs create-queue`                       | Create a new SQS queue                       |
| `aws sqs list-queues`                        | List all SQS queues                          |
| `aws sqs send-message`                       | Send a message to an SQS queue               |
| `aws sqs receive-message`                    | Retrieve a message from an SQS queue         |
| `aws sqs delete-message`                     | Delete a message from an SQS queue           |
| `aws sqs purge-queue`                        | Delete all messages in an SQS queue          |
| `aws sqs set-queue-attributes`               | Set attributes for an SQS queue              |
| `aws sqs get-queue-attributes`               | Retrieve attributes of an SQS queue          |

## Key Terms
- **Queue**: A temporary repository for messages that are awaiting processing.
- **Visibility Timeout**: The period during which a message is invisible to other consumers.
- **Delay Queue**: A queue that postpones the delivery of new messages.
- **Dead-Letter Queue**: A queue for messages that fail to be processed successfully.

## Best Practices
- **Use FIFO Queues for Order-Sensitive Tasks**: Ensure messages are processed in order.
- **Implement Dead-Letter Queues**: Capture messages that fail to be processed.
- **Monitor Queue Metrics**: Use CloudWatch to monitor and manage queues.
- **Secure Your Queues**: Use IAM policies and encryption.
- **Optimize Visibility Timeout**: Set an appropriate visibility timeout to prevent message duplication.

## Example: Creating a Standard Queue
```bash
aws sqs create-queue \
    --queue-name my-standard-queue


aws sqs create-queue \
    --queue-name my-fifo-queue.fifo \
    --attributes FifoQueue=true


aws sqs send-message \
    --queue-url https://sqs.us-east-1.amazonaws.com/123456789012/my-queue \
    --message-body "This is a test message"


aws sqs receive-message \
    --queue-url https://sqs.us-east-1.amazonaws.com/123456789012/my-queue


aws sqs delete-message \
    --queue-url https://sqs.us-east-1.amazonaws.com/123456789012/my-queue \
    --receipt-handle AQEB1234567890


aws sqs set-queue-attributes \
    --queue-url https://sqs.us-east-1.amazonaws.com/123456789012/my-queue \
    --attributes VisibilityTimeout=60


aws sqs set-queue-attributes \
    --queue-url https://sqs.us-east-1.amazonaws.com/123456789012/my-queue \
    --attributes RedrivePolicy='{"maxReceiveCount":"5", "deadLetterTargetArn":"arn:aws:sqs:us-east-1:123456789012:my-dlq"}'
