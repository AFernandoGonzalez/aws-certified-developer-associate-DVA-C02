# AWS X-Ray Cheat Sheet

## Overview
AWS X-Ray helps developers analyze and debug distributed applications in production or under development. With X-Ray, you can understand how your application and its underlying services are performing to identify and troubleshoot performance issues and errors.

## Use Cases
- **Performance Optimization**: Identify performance bottlenecks in your applications.
- **Error Tracing**: Pinpoint where errors are occurring and understand their root causes.
- **Service Map Visualization**: Visualize the interactions between application components.
- **Distributed Tracing**: Trace requests as they travel through multiple services.

## Key Features
- **Distributed Tracing**: Track requests across various services and applications.
- **Service Maps**: Visualize components of your application and their interactions.
- **Annotations and Metadata**: Add custom annotations and metadata for advanced analysis.
- **Filtering**: Filter traces based on specific criteria.
- **Trace Segments and Subsegments**: Break down traces into segments and subsegments for detailed analysis.
- **Latency Analysis**: Identify latency issues within your application.

## Key Concepts

### Traces
- **Trace**: Records the path of a request as it travels through your application.
- **Segment**: A single unit of work in your application (e.g., an API call).
- **Subsegment**: A subunit of a segment, often used to provide more granular details.
- **Annotations**: Key-value pairs that you can use to filter and group traces.
- **Metadata**: Non-queryable data attached to segments and subsegments for additional context.

### Service Map
- **Service Map**: A visual representation of your application’s components and their interactions.

### Sampling
- **Sampling**: Controls the amount of data that AWS X-Ray records, helping manage costs and performance impacts.

## Monitoring and Metrics
- **Trace Data**: Collect trace data to monitor application performance.
- **Service Maps**: Use service maps to visualize and understand application architecture.
- **Filtering and Grouping**: Filter and group trace data using annotations and metadata for targeted analysis.

## Security
- **IAM Policies**: Control access to AWS X-Ray resources using IAM policies.
- **Encryption**: Data in transit is encrypted using SSL/TLS.
- **Data Protection**: Ensure sensitive data is not inadvertently included in trace data.

## Pricing
- **Free Tier**: Includes 100,000 traces recorded and scanned per month.
- **Paid Tier**: Additional traces are charged per million traces recorded and scanned.

## Key Terms
- **Trace**: A record of a request through your application.
- **Segment**: A unit of work within a trace.
- **Subsegment**: A finer-grained unit of work within a segment.
- **Service Map**: Visualization of your application's components and their interactions.

## Best Practices
- **Use Annotations and Metadata**: Add annotations and metadata to enrich trace data.
- **Optimize Sampling**: Adjust sampling rates to balance between cost and the level of detail.
- **Monitor Performance**: Use X-Ray insights to continuously monitor and improve application performance.
- **Secure Trace Data**: Use IAM policies to control access and ensure sensitive data is not included in traces.

## Example: Instrumenting an Application with AWS X-Ray

### Step 1: Enable X-Ray
1. Sign in to the AWS Management Console.
2. Navigate to the AWS X-Ray console.
3. Enable X-Ray for your AWS account.

### Step 2: Instrument Your Application
1. Use the AWS X-Ray SDK to instrument your application.
2. Import the X-Ray SDK into your application code.
3. Configure the SDK to capture trace data.
4. Instrument your code by adding trace segments and subsegments.

### Step 3: View Traces
1. Navigate to the X-Ray console.
2. Choose "Traces" from the navigation pane.
3. Use the filter options to find specific traces.
4. Analyze the trace details to identify performance issues and errors.

### Step 4: Visualize the Service Map
1. Navigate to the X-Ray console.
2. Choose "Service map" from the navigation pane.
3. View the interactions between your application's components.
4. Identify performance bottlenecks and dependencies.

### Example: Using X-Ray with Lambda
### Step 1: Enable Active Tracing
1. Navigate to the Lambda console.
2. Choose your function.
3. Under "Configuration", choose "Monitoring and operations tools".
4. Enable "Active tracing".

### Step 2: View Traces in the X-Ray Console
1. Invoke your Lambda function.
2. Navigate to the X-Ray console.
3. View the traces and analyze the performance of your Lambda function.

## Example: Creating a Segment

```python
import boto3
from aws_xray_sdk.core import xray_recorder
from aws_xray_sdk.core import patch_all

# Patch all supported libraries to instrument them
patch_all()

# Start a new segment
segment = xray_recorder.begin_segment('my_segment')

# Add metadata and annotations
segment.put_metadata('key', 'value')
segment.put_annotation('key', 'value')

# End the segment
xray_recorder.end_segment()
