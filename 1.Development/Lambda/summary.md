# AWS Lambda Cheat Sheet

## Overview
AWS Lambda is a serverless compute service that runs your code in response to events and automatically manages the underlying compute resources.

## Use Cases
- Real-time file processing (e.g., image resizing, transcoding)
- Data transformations (e.g., stream processing)
- Real-time data processing (e.g., IoT data streams)
- Event-driven applications (e.g., backend services, microservices)

## Key Features
- **Event-driven**: Trigger functions in response to various events.
- **Serverless**: No need to manage servers or infrastructure.
- **Automatic Scaling**: Automatically scales the execution in response to incoming requests.
- **Supports Multiple Languages**: Python, Node.js, Java, C#, Go, Ruby, etc.
- **Integrations**: Easily integrates with other AWS services.

## Key Concepts

### Functions
- **Function**: The code you want to run on AWS Lambda.
- **Handler**: The method in your function that AWS Lambda invokes.
- **Runtime**: The language runtime to execute your function.

### Triggers
- **Triggers**: Sources that invoke your Lambda function.
  - **S3**: Trigger on S3 events (e.g., object creation).
  - **API Gateway**: Trigger on HTTP requests.
  - **CloudWatch Events**: Trigger on schedule or system events.
  - **DynamoDB Streams**: Trigger on stream events.
  - **SNS**: Trigger on messages.

### Execution Environment
- **Execution Role**: IAM role that Lambda assumes when it executes your function.
- **Environment Variables**: Key-value pairs passed to your function.
- **Memory Allocation**: The amount of memory allocated to your function (128 MB to 10 GB).

### Layers
- **Lambda Layers**: Zip files containing libraries, custom runtimes, or other dependencies that can be used by your Lambda function.

## Lambda Function Lifecycle
- **Create**: Write and upload your code, configure triggers and settings.
- **Invoke**: Lambda runs your function in response to triggers.
- **Monitor**: Use CloudWatch to monitor execution and performance.
- **Update**: Modify the function code, configuration, or triggers.
- **Delete**: Remove the function and associated resources.

## Deployment
- **Inline Code**: Write code directly in the Lambda console.
- **Zip File**: Upload a zip file containing your code and dependencies.
- **Container Image**: Deploy your function code as a container image.

## Monitoring and Logging
- **CloudWatch Logs**: Automatically logs function invocations and error messages.
- **CloudWatch Metrics**: Provides metrics such as invocations, errors, duration, and throttles.
- **AWS X-Ray**: Trace and analyze requests as they travel through your application.

## Pricing
- **Free Tier**: 1 million free requests and 400,000 GB-seconds of compute time per month.
- **Pay-As-You-Go**: Charges based on the number of requests and the duration of code execution.
  - **Requests**: $0.20 per 1 million requests.
  - **Duration**: $0.00001667 per GB-second.

## Common Commands
| Command                                    | Description                                         |
|--------------------------------------------|-----------------------------------------------------|
| `aws lambda list-functions`                | List all Lambda functions                           |
| `aws lambda create-function`               | Create a new Lambda function                        |
| `aws lambda update-function-code`          | Update the code of an existing Lambda function      |
| `aws lambda delete-function`               | Delete a Lambda function                            |
| `aws lambda invoke --function-name <name>` | Invoke a Lambda function manually                   |

## Key Terms
- **Cold Start**: Initial start of a Lambda function instance; takes longer.
- **Warm Start**: Reuse of a Lambda function instance; faster execution.
- **Concurrency**: Number of function executions that run simultaneously.
- **Provisioned Concurrency**: Pre-warms instances to reduce cold start latency.

## Best Practices
- **Optimize Function Code**: Minimize package size and dependencies.
- **Use Environment Variables**: Manage configuration settings.
- **Monitor and Log**: Utilize CloudWatch Logs and Metrics for insights.
- **Secure Your Function**: Use IAM roles and least privilege policies.
- **Manage Concurrency**: Use reserved concurrency to control limits.

## Example: Creating a Lambda Function
```python
import json

def lambda_handler(event, context):
    # TODO implement
    return {
        'statusCode': 200,
        'body': json.dumps('Hello from Lambda!')
    }
