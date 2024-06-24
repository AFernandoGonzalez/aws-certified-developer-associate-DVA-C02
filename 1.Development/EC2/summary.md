Here's a comprehensive cheat sheet for EC2 in Markdown format, including tables and structured information for clarity:

```markdown
# EC2 (Elastic Compute Cloud) Cheat Sheet

## Overview

EC2 provides resizable compute capacity in the cloud. It allows you to launch and manage virtual servers.

## Use Cases

- Hosting applications
- Running compute-intensive workloads
- Web hosting

## Key Features

- Various instance types optimized for different use cases
- Elastic Block Store (EBS) for persistent storage
- Instance Store: Ephemeral storage
- Security Groups for inbound and outbound traffic control

## Instance Types

| Instance Family   | Use Case                                 | Example Instance Types |
| ----------------- | ---------------------------------------- | ---------------------- |
| General Purpose   | Balanced compute, memory, and networking | t3, m5, t3a, m6g       |
| Compute Optimized | Compute-bound applications               | c5, c5n, c6g           |
| Memory Optimized  | Memory-bound applications                | r5, x1e, r6g           |
| Storage Optimized | High I/O operations                      | i3, d2, h1             |
| GPU Instances     | Graphics-intensive applications          | p3, g4ad, g4dn         |
| HPC Instances     | High-Performance Computing               | hpc6a, hpc6id          |

## Storage Options

| Storage Type              | Description                                | Use Cases                          |
| ------------------------- | ------------------------------------------ | ---------------------------------- |
| EBS (Elastic Block Store) | Persistent block storage for EC2 instances | Databases, file systems, backups   |
| Instance Store            | Temporary block storage for EC2 instances  | Caching, temporary data            |
| EFS (Elastic File System) | Managed file storage for EC2 instances     | Shared storage, content management |

## Security Features

- **Security Groups**: Virtual firewall to control inbound and outbound traffic.
- **Key Pairs**: Secure SSH access to instances.
- **IAM Roles**: Grant permissions to instances to access AWS services.

## Key Concepts

### Launching an Instance

1. **Choose AMI (Amazon Machine Image)**: Preconfigured template for your instance.
2. **Choose Instance Type**: Select the type based on your use case.
3. **Configure Instance**: Set up network, IAM role, shutdown behavior, etc.
4. **Add Storage**: Attach EBS volumes or instance store.
5. **Add Tags**: Metadata to help manage instances.
6. **Configure Security Group**: Set up firewall rules.
7. **Review and Launch**: Finalize settings and launch instance.

### EC2 Pricing

| Pricing Model  | Description                                                                                  |
| -------------- | -------------------------------------------------------------------------------------------- |
| On-Demand      | Pay for compute capacity by the hour or second                                               |
| Reserved       | Significant discount for committing to use for 1 or 3 years                                  |
| Spot Instances | Bid for unused EC2 capacity at a reduced rate                                                |
| Savings Plans  | Flexible pricing model offering lower prices on a commitment to a consistent amount of usage |

### Elastic IP Addresses

- **Elastic IP**: Static IP address for dynamic cloud computing.
- **Use Cases**: Re-mapping instances in case of instance failure or updates.

### Auto Scaling

- **Auto Scaling Group**: Collection of instances treated as a logical group for scaling and management.
- **Scaling Policies**: Define when and how to scale instances (e.g., based on CPU usage).

## Monitoring and Management

- **CloudWatch**: Monitor instance performance (CPU, memory, disk, network).
- **CloudTrail**: Track user activity and API usage.
- **Systems Manager**: Manage and automate operational tasks across your AWS resources.

### Common Commands

| Command                       | Description                  |
| ----------------------------- | ---------------------------- |
| `aws ec2 describe-instances`  | Lists all your EC2 instances |
| `aws ec2 start-instances`     | Starts an EC2 instance       |
| `aws ec2 stop-instances`      | Stops an EC2 instance        |
| `aws ec2 terminate-instances` | Terminates an EC2 instance   |
| `aws ec2 reboot-instances`    | Reboots an EC2 instance      |

### Key Terms

- **AMI (Amazon Machine Image)**: Preconfigured templates for your instances.
- **VPC (Virtual Private Cloud)**: Virtual network dedicated to your AWS account.
- **EBS (Elastic Block Store)**: Persistent block storage for use with EC2 instances.
- **Elastic IP**: Static IP address designed for dynamic cloud computing.

### Best Practices

- **Use IAM roles** to securely grant permissions to your instances.
- **Regularly monitor** instance performance with CloudWatch.
- **Automate backups** using EBS snapshots.
- **Implement security groups** to control traffic to your instances.
- **Tag your resources** for better management and cost tracking.


