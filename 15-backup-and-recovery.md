# Backup & Recovery

# Disaster Recovery

- Recovery Point Objective (RPO): Has to do with data loss; when was data last backed up BEFORE a disaster?
- Recovery Time Objective (RTO): Related to the downtime AFTER a disaster
- Pilot Light
    - Tens of minutes: start and scale resources after an event (core services)
- Warm Standby
    - Minutes: scale resources after an event (business critical services)
- Multi-site/Active-Active: Zero downtime (mission critical services)

# Data Lifecycle Manager

- Used for backup and recovery of EBS volumes (only)

- Used for EBS Volume Snapshots automation
- Features
    - Define policies for snapshot creation and retention
    - Automate backup retention lifecycle
    - Reduce storage costs with automatic expiration
- Ideal for stateful workloads needing periodic backups

# AWS Backup

- Used to do backups for multiple services (EBS, EFS, RDS, etc.) all from a single interface

- Fully managed backup service for AWS workloads
- Features
    - Centralised backup management
    - Policy-based backup schedules
    - Cross-region & cross-account backups
- Supported Services: RDS, DynamoDB, EBS, S3, EFS, and more

# Backup and Restore with RDS

- Automated backups; RDS does a full daily snapshot (single region)
- Snapshots; user-initiated (cross-region)
- Read replicas (cross-region)
- Restoration
    - To a point in time
    - From a snapshot
    - Promoting a read replica

- Automated backups (retention up to 35 days)
- Manual snapshots (retained indefinitely)
- Point-in-time recovery (PITR) within backup retention period
- Backups stored in S3
- Cross-region snapshot copy for DR

# Backup and Restore with Aurora

- Generally going to be faster and require less effort
- Multi-Master: All DB instances have read/write capability (single region)
    - If writer becomes unavailable, another takes over
- Global Database: Spans up to 5 regions
    - During failover, a secondary region promoted to primary

- Continuous, incremental backups to Amazon S3
- Automatic failover across Aurora replicas
- Point-in-time recovery with a continuous backup model
- Faster restore compared to traditonal RDS due to distributed storage

