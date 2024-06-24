# AWS API Gateway Cheat Sheet

## Overview
AWS API Gateway is a fully managed service that makes it easy for developers to create, publish, maintain, monitor, and secure APIs at any scale.

## Use Cases
- Create RESTful APIs
- Create WebSocket APIs
- Create HTTP APIs
- Serverless backend for web, mobile, and IoT applications

## Key Features
- **RESTful API Creation**: Create and manage REST APIs.
- **WebSocket API Creation**: Real-time, two-way communication applications.
- **HTTP APIs**: Lower cost, higher performance alternative for REST APIs.
- **API Throttling**: Control the rate of requests.
- **CORS Support**: Configure cross-origin resource sharing.
- **API Caching**: Reduce the number of calls made to backend services.
- **Stages and Deployment**: Manage different stages of API development and deployment.
- **Custom Domain Names**: Use custom domain names for APIs.
- **Authentication and Authorization**: Use IAM, Cognito, and Lambda authorizers.

## Key Concepts

### API Types
- **REST APIs**: Representational State Transfer APIs, supporting CRUD operations.
- **WebSocket APIs**: Real-time, bi-directional communication.
- **HTTP APIs**: Optimized for HTTP endpoints, with lower latency and cost.

### Integration Types
- **Lambda Proxy Integration**: Directly integrate with Lambda functions.
- **HTTP Integration**: Forward requests to HTTP endpoints.
- **Mock Integration**: Return a response without sending the request to the backend.
- **AWS Service Integration**: Directly call other AWS services.

### Throttling and Quotas
- **Throttling**: Limits the steady-state request rate.
- **Quotas**: Limits the number of requests in a given period.

### Security
- **IAM Roles and Policies**: Control access to APIs.
- **Cognito User Pools**: Authenticate API calls.
- **Lambda Authorizers**: Custom authorization logic.
- **API Keys**: Identify and track API consumers.

### Caching
- **API Caching**: Cache responses to improve performance and reduce backend load.

## Deployment and Management
- **Stages**: Isolate different environments (e.g., dev, test, prod).
- **Deployments**: Deploy API changes to a specific stage.
- **Custom Domain Names**: Map custom domain names to your APIs.
- **Usage Plans**: Define plans to manage API usage and quotas.

## Monitoring and Logging
- **CloudWatch Logs**: Monitor API requests and errors.
- **CloudWatch Metrics**: Track performance metrics.
- **X-Ray**: Trace and debug API requests.

## Pricing
- **Free Tier**: 1 million REST API calls per month.
- **Pay-As-You-Go**: Charges based on the number of API calls, data transfer, and caching.

## Common Commands
| Command                                              | Description                                     |
|------------------------------------------------------|-------------------------------------------------|
| `aws apigateway create-rest-api`                     | Create a new REST API                           |
| `aws apigateway get-rest-apis`                       | List all REST APIs                              |
| `aws apigateway create-resource`                     | Create a resource                               |
| `aws apigateway put-method`                          | Add a method to a resource                      |
| `aws apigateway create-deployment`                   | Deploy an API to a stage                        |
| `aws apigateway create-api-key`                      | Create an API key                               |
| `aws apigateway create-usage-plan`                   | Create a usage plan                             |

## Key Terms
- **Endpoint**: The URL of the API.
- **Resource**: A specific path in the API (e.g., `/users`).
- **Method**: HTTP method (GET, POST, PUT, DELETE) associated with a resource.
- **Integration**: Connection between the method and the backend.
- **Stage**: Represents a version of the deployed API.
- **Deployment**: The act of publishing the API to a stage.

## Best Practices
- **Use Stages**: Separate different environments (e.g., dev, test, prod).
- **Enable Caching**: Improve performance and reduce backend load.
- **Implement Rate Limiting**: Protect your backend from being overwhelmed.
- **Use Custom Domain Names**: Provide a user-friendly API endpoint.
- **Secure Your APIs**: Use IAM roles, Cognito, and Lambda authorizers.
- **Monitor API Usage**: Use CloudWatch Logs and Metrics.

## Example: Creating a Simple REST API
```bash
# Create a REST API
aws apigateway create-rest-api --name 'MyAPI' --description 'My first API'

# Get the API ID
API_ID=$(aws apigateway get-rest-apis --query 'items[?name==`MyAPI`].id' --output text)

# Create a Resource
PARENT_ID=$(aws apigateway get-resources --rest-api-id $API_ID --query 'items[?path==`/`].id' --output text)
RESOURCE_ID=$(aws apigateway create-resource --rest-api-id $API_ID --parent-id $PARENT_ID --path-part 'resource' --query 'id' --output text)

# Create a Method
aws apigateway put-method --rest-api-id $API_ID --resource-id $RESOURCE_ID --http-method GET --authorization-type 'NONE'

# Create a Lambda Function (Assuming Lambda function already exists)
aws apigateway put-integration --rest-api-id $API_ID --resource-id $RESOURCE_ID --http-method GET --type AWS_PROXY --integration-http-method POST --uri 'arn:aws:apigateway:region:lambda:path/2015-03-31/functions/arn:aws:lambda:region:account-id:function:my-function/invocations'

# Deploy the API
aws apigateway create-deployment --rest-api-id $API_ID --stage-name 'dev'
