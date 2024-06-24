# DynamoDB Cheat Sheet

## Overview
Amazon DynamoDB is a fully managed NoSQL database service that provides fast and predictable performance with seamless scalability.

## Use Cases
- Real-time data processing
- Mobile and web applications
- IoT applications
- Gaming applications

## Key Features
- **Fully Managed**: No server management required.
- **High Performance**: Low-latency performance for high-scale applications.
- **Flexible Schema**: No need to define the structure of data beforehand.
- **Integrated Security**: Encryption at rest and in transit, IAM for access control.
- **Global Tables**: Multi-region replication for globally distributed applications.
- **Streams**: Change data capture for event-driven architectures.
- **Backup and Restore**: Automated backup and restore capabilities.
- **TTL (Time to Live)**: Automatically delete expired data.

## Key Concepts

### Tables and Items
- **Table**: A collection of data.
- **Item**: A single data record in a table (equivalent to a row in a relational database).
- **Attribute**: A single data element within an item (equivalent to a column in a relational database).

### Primary Keys
- **Partition Key**: A single attribute primary key.
- **Composite Key**: A combination of partition key and sort key.

### Data Types
- **Scalar Types**: String, Number, Binary, Boolean, Null.
- **Document Types**: List, Map.
- **Set Types**: String Set, Number Set, Binary Set.

### Secondary Indexes
- **Global Secondary Index (GSI)**: An index with a partition key and an optional sort key that can be different from those on the base table.
- **Local Secondary Index (LSI)**: An index with the same partition key as the base table but a different sort key.

## Provisioned and On-Demand Capacity
- **Provisioned Capacity**: Specify the number of reads and writes per second.
- **On-Demand Capacity**: Pay-per-request pricing model.

## Streams and Triggers
- **DynamoDB Streams**: Capture changes to items in a table.
- **Triggers**: Use AWS Lambda to process stream records.

## Data Management
- **Batch Operations**: BatchWriteItem, BatchGetItem.
- **Transactions**: ACID transactions for coordinated, all-or-nothing operations.

## Security
- **IAM Policies**: Fine-grained access control.
- **Encryption**: Server-side encryption using AWS KMS.
- **VPC Endpoints**: Connect DynamoDB to your VPC.

## Monitoring and Metrics
- **CloudWatch Metrics**: Monitor read/write capacity, latency, throttled requests.
- **CloudTrail**: Track API calls made to DynamoDB.

## Pricing
- **Free Tier**: 25 GB of storage, 25 read capacity units, 25 write capacity units.
- **Provisioned Capacity**: Pay for reserved read and write capacity.
- **On-Demand Capacity**: Pay per request.

## Common Commands
| Command                                              | Description                                     |
|------------------------------------------------------|-------------------------------------------------|
| `aws dynamodb create-table`                          | Create a new DynamoDB table                     |
| `aws dynamodb list-tables`                           | List all DynamoDB tables                        |
| `aws dynamodb put-item`                              | Insert a new item into a table                  |
| `aws dynamodb get-item`                              | Retrieve an item from a table                   |
| `aws dynamodb update-item`                           | Update an existing item in a table              |
| `aws dynamodb delete-item`                           | Delete an item from a table                     |

## Key Terms
- **RCU (Read Capacity Unit)**: One strongly consistent read per second for an item up to 4 KB in size.
- **WCU (Write Capacity Unit)**: One write per second for an item up to 1 KB in size.
- **Eventually Consistent Reads**: Reads that might not reflect the most recent write.
- **Strongly Consistent Reads**: Reads that return the most up-to-date data.

## Best Practices
- **Design for Scale**: Use partition keys and sort keys effectively.
- **Optimize Read/Write Capacity**: Monitor and adjust capacity units.
- **Use Indexes Wisely**: Create GSIs and LSIs to optimize query performance.
- **Leverage DynamoDB Streams**: Implement event-driven architectures.
- **Secure Your Data**: Use IAM policies, encryption, and VPC endpoints.
- **Monitor and Analyze**: Utilize CloudWatch and CloudTrail.

## Example: Creating a DynamoDB Table
```bash
aws dynamodb create-table \
    --table-name MusicCollection \
    --attribute-definitions \
        AttributeName=Artist,AttributeType=S \
        AttributeName=SongTitle,AttributeType=S \
    --key-schema \
        AttributeName=Artist,KeyType=HASH \
        AttributeName=SongTitle,KeyType=RANGE \
    --provisioned-throughput \
        ReadCapacityUnits=5,WriteCapacityUnits=5

aws dynamodb put-item \
    --table-name MusicCollection \
    --item \
        '{"Artist": {"S": "No One You Know"}, "SongTitle": {"S": "Call Me Today"}, "AlbumTitle": {"S": "Somewhat Famous"}}'

aws dynamodb query \
    --table-name MusicCollection \
    --key-condition-expression "Artist = :artist" \
    --expression-attribute-values  '{":artist":{"S":"No One You Know"}}'
```

## Example: Creating a Lambda Function
```python
import boto3
dynamodb = boto3.resource('dynamodb')
table = dynamodb.Table('MusicCollection')

def lambda_handler(event, context):
    response = table.get_item(
        Key={
            'Artist': 'No One You Know',
            'SongTitle': 'Call Me Today'
        }
    )
    item = response['Item']
    return item
```