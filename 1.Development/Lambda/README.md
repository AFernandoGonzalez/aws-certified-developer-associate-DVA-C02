# Lambda

## Overview
- Serverless computing to run code without provisioning servers.
- Triggered by events from other AWS services (S3, DynamoDB, Kinesis, etc.).

## Common Commands

### Creating a Lambda Function
```bash
aws lambda create-function --function-name my-function --runtime python3.8 --role arn:aws:iam::account-id:role/execution_role --handler lambda_function.lambda_handler --zip-file fileb://function.zip
```

### Invoking a Lambda Function
```bash
aws lambda invoke --function-name my-function out.txt
```

## Examples
See the [examples](./examples) folder for practical scripts and use cases.
