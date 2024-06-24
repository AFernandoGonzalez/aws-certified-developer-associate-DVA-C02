# Amazon Kinesis Cheat Sheet

## Overview
Amazon Kinesis is a platform for real-time data streaming and processing. It enables you to collect, process, and analyze real-time, streaming data.

## Use Cases
- Real-time analytics
- Log and event data collection
- Real-time metrics and reporting
- Real-time data ingestion for machine learning

## Key Features
- **Real-Time Processing**: Low-latency data ingestion and processing.
- **Scalability**: Automatically scales to match the throughput of your data.
- **Data Retention**: Configurable data retention period.
- **Integration**: Easily integrates with AWS services such as Lambda, S3, Redshift, and more.

## Key Services

### Kinesis Data Streams (KDS)
- **Streams**: Continuous and highly available data streams.
- **Shards**: A stream is divided into shards, each providing a fixed unit of capacity.
- **Producers**: Applications that write data to the stream.
- **Consumers**: Applications that read and process data from the stream.

### Kinesis Data Firehose
- **Fully Managed Service**: Automatically scales to match the throughput of your data.
- **Data Transformation**: Supports Lambda functions for data transformation.
- **Destinations**: Delivers data to S3, Redshift, Elasticsearch, and Splunk.

### Kinesis Data Analytics
- **Real-Time SQL Queries**: Process streaming data using standard SQL.
- **Integrations**: Integrates with Kinesis Data Streams and Kinesis Data Firehose.
- **Windowed Queries**: Supports time-based and count-based windows for aggregation.

### Kinesis Video Streams
- **Video Streams**: Ingest, process, and store video streams.
- **Playback**: Play video streams in real-time or on demand.
- **Integration**: Integrates with AWS services like Rekognition for video analysis.

## Key Concepts

### Shards
- **Shard**: A unit of capacity in a Kinesis Data Stream.
- **Capacity**: Each shard can ingest up to 1 MB of data per second and emit up to 2 MB of data per second.
- **Shard Iterator**: A pointer to the current location in the shard.

### Producers and Consumers
- **Producer**: Writes data to Kinesis Data Streams.
- **Consumer**: Reads and processes data from Kinesis Data Streams.
- **Enhanced Fan-Out**: Allows consumers to receive data with dedicated throughput.

## Security
- **IAM Policies**: Fine-grained access control for producers and consumers.
- **Encryption**: Server-side encryption using AWS KMS.
- **VPC Endpoints**: Securely connect to Kinesis within your VPC.

## Monitoring and Metrics
- **CloudWatch Metrics**: Monitor stream capacity, incoming data, and outgoing data.
- **CloudWatch Logs**: Log data from Kinesis for monitoring and troubleshooting.
- **Enhanced Monitoring**: Detailed monitoring for stream-level metrics.

## Pricing
- **Kinesis Data Streams**: Based on the number of shards and PUT payload units.
- **Kinesis Data Firehose**: Based on the volume of data ingested and delivered.
- **Kinesis Data Analytics**: Based on the number of Kinesis Processing Units (KPU) used.

## Common Commands
| Command                                                  | Description                                     |
|----------------------------------------------------------|-------------------------------------------------|
| `aws kinesis create-stream`                              | Create a new Kinesis stream                     |
| `aws kinesis describe-stream`                            | Describe a Kinesis stream                       |
| `aws kinesis put-record`                                 | Put a single record into a Kinesis stream       |
| `aws kinesis get-records`                                | Get records from a Kinesis stream               |
| `aws firehose create-delivery-stream`                    | Create a new Firehose delivery stream           |
| `aws firehose describe-delivery-stream`                  | Describe a Firehose delivery stream             |
| `aws kinesisanalytics create-application`                | Create a Kinesis Data Analytics application     |
| `aws kinesisanalytics describe-application`              | Describe a Kinesis Data Analytics application   |

## Key Terms
- **Shard**: A unit of capacity in a stream.
- **Partition Key**: Determines the shard where data is stored.
- **Sequence Number**: Unique identifier for each record within a shard.
- **Kinesis Processing Unit (KPU)**: Unit of capacity for Kinesis Data Analytics.

## Best Practices
- **Design for Scale**: Distribute data evenly across shards using partition keys.
- **Monitor Metrics**: Use CloudWatch to monitor stream health and performance.
- **Optimize Shard Count**: Adjust the number of shards to match your throughput needs.
- **Secure Your Data**: Use IAM policies, encryption, and VPC endpoints.

## Example: Creating a Kinesis Stream
```bash
aws kinesis create-stream \
    --stream-name my-stream \
    --shard-count 1

aws kinesis put-record \
    --stream-name my-stream \
    --partition-key my-partition-key \
    --data "sample data"

aws firehose create-delivery-stream \
    --delivery-stream-name my-firehose \
    --s3-destination-configuration RoleARN=arn:aws:iam::123456789012:role/firehose-role,BucketARN=arn:aws:s3:::my-bucket,Prefix="my-prefix/"


aws kinesisanalytics create-application \
    --application-name my-application \
    --inputs "[{\"NamePrefix\": \"exampleNamePrefix\", \"KinesisStreamsInput\": {\"ResourceARN\": \"arn:aws:kinesis:us-east-1:123456789012:stream/exampleStream\", \"RoleARN\": \"arn:aws:iam::123456789012:role/service-role/my-role\"}}]"
