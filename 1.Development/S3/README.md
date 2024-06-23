# S3 (Simple Storage Service)

## Overview
- Object storage service with high availability.
- Storage classes: Standard, Intelligent-Tiering, Standard-IA, One Zone-IA, Glacier, Glacier Deep Archive.

## Common Commands

### Creating an S3 Bucket
```bash
aws s3 mb s3://my-bucket
```

### Uploading a File to S3
```bash
aws s3 cp myfile.txt s3://my-bucket/
```

## Examples
See the [examples](./examples) folder for practical scripts and use cases.
