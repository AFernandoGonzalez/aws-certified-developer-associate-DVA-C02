# AWS RDS Cheat Sheet

## Overview
Amazon Relational Database Service (RDS) is a managed relational database service that supports several database engines, including MySQL, PostgreSQL, MariaDB, Oracle, SQL Server, and Amazon Aurora.

## Use Cases
- Web and mobile applications
- E-commerce platforms
- Business applications
- Data warehousing and analytics

## Key Features
- **Managed Service**: Automated backups, patching, and updates.
- **Multi-AZ Deployments**: High availability and failover support.
- **Read Replicas**: Improve read scalability and performance.
- **Automated Backups**: Scheduled backups with point-in-time recovery.
- **Manual Snapshots**: User-initiated backups.
- **Encryption**: Data encryption at rest and in transit.
- **Monitoring**: Integration with Amazon CloudWatch for metrics and logs.
- **Security**: Network isolation using VPC, IAM integration, and database firewall rules.
- **Scaling**: Easy to scale compute and storage.

## Key Concepts

### Database Instances
- **DB Instance**: A database environment in the cloud.
- **DB Instance Class**: Specifies the compute and memory capacity (e.g., db.t2.micro, db.m5.large).
- **Storage**: Types include General Purpose (SSD), Provisioned IOPS (SSD), and Magnetic.

### Database Engines
- **Amazon Aurora**: MySQL and PostgreSQL-compatible, high-performance database.
- **MySQL**: Popular open-source database.
- **PostgreSQL**: Advanced open-source database with a wide range of features.
- **MariaDB**: Open-source database, fork of MySQL.
- **Oracle**: Commercial database with enterprise features.
- **SQL Server**: Microsoft's relational database.

### Availability and Durability
- **Multi-AZ Deployment**: Automatically creates a standby replica in a different Availability Zone.
- **Read Replicas**: Allow read-heavy workloads to be distributed across multiple instances.

### Backup and Restore
- **Automated Backups**: Daily backups and transaction logs.
- **Manual Snapshots**: User-initiated snapshots for backup.

## Security
- **IAM Policies**: Fine-grained access control.
- **Encryption**: Data encryption at rest using AWS KMS and in transit using SSL/TLS.
- **Network Isolation**: Using Amazon VPC for network security.

## Monitoring and Metrics
- **CloudWatch Metrics**: Monitor performance and resource utilization.
- **Enhanced Monitoring**: Real-time monitoring for OS metrics.
- **RDS Performance Insights**: Analyze and tune database performance.

## Pricing
- **On-Demand Instances**: Pay-per-use model.
- **Reserved Instances**: Lower cost with commitment to a one-year or three-year term.
- **Storage**: Charges based on the type and amount of storage.
- **Data Transfer**: Charges for data transfer in and out of RDS.

## Common Commands
| Command                                              | Description                                     |
|------------------------------------------------------|-------------------------------------------------|
| `aws rds create-db-instance`                         | Create a new RDS instance                       |
| `aws rds describe-db-instances`                      | Describe RDS instances                          |
| `aws rds delete-db-instance`                         | Delete an RDS instance                          |
| `aws rds create-db-snapshot`                         | Create a manual snapshot                        |
| `aws rds restore-db-instance-from-db-snapshot`       | Restore an instance from a snapshot             |
| `aws rds create-db-instance-read-replica`            | Create a read replica                           |

## Key Terms
- **DB Instance**: A database environment in the cloud.
- **Multi-AZ**: Deployment option for high availability.
- **Read Replica**: Read-only copy of the database for scaling read traffic.
- **DB Parameter Group**: A group of engine configuration values.
- **DB Subnet Group**: A collection of subnets for a DB instance in a VPC.

## Best Practices
- **Use Multi-AZ for High Availability**: Ensure availability and automatic failover.
- **Enable Automated Backups**: Protect data with regular backups.
- **Use Read Replicas for Read Scalability**: Distribute read traffic across multiple instances.
- **Monitor Performance**: Use CloudWatch and Performance Insights.
- **Secure Your Database**: Use IAM, encryption, and VPC.

## Example: Creating an RDS MySQL Instance
```bash
aws rds create-db-instance \
    --db-instance-identifier mydatabase \
    --db-instance-class db.t2.micro \
    --engine mysql \
    --master-username admin \
    --master-user-password mypassword \
    --allocated-storage 20 \
    --backup-retention-period 7 \
    --no-multi-az \
    --publicly-accessible \
    --vpc-security-group-ids sg-xxxxxxxx


aws rds create-db-instance-read-replica \
    --db-instance-identifier myreadreplica \
    --source-db-instance-identifier mydatabase \
    --db-instance-class db.t2.micro \
    --availability-zone us-west-2a


aws rds restore-db-instance-from-db-snapshot \
    --db-instance-identifier myrestoredinstance \
    --db-snapshot-identifier mydbsnapshot


aws rds delete-db-instance \
    --db-instance-identifier mydatabase \
    --skip-final-snapshot
