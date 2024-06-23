# EC2 (Elastic Compute Cloud)

## Overview
- Launch and manage virtual servers.
- EBS (Elastic Block Store): Persistent block storage.
- Instance Store: Ephemeral storage.

## Common Commands

### Launching an EC2 Instance
```bash
aws ec2 run-instances --image-id ami-0123456789abcdef0 --count 1 --instance-type t2.micro --key-name MyKeyPair --security-group-ids sg-12345678 --subnet-id subnet-6e7f829e
```

### Stopping an EC2 Instance
```bash
aws ec2 stop-instances --instance-ids i-1234567890abcdef0
```

## Examples
See the [examples](./examples) folder for practical scripts and use cases.
