# Databases

# Relational Database Service (RDS)

Managed relational databse service supporting databases like MySQL, PostgreSQL, MariaDB, Oracle, and SQL Server. Focus on automated backups, Multi-AZ deployments, and read replicas

- Relational data service with six engines available (Aurora, MySQL, PostgreSQL, etc.)
- Managed database service
    - AWS does all the underlying administrative work
    - You are responsible for network access and managing database users and permissions
- Read replicas used for read-heavy applications, where read-only traffic is directed to the replica, alleviating traffic from the primary database
    - Also works cross-region
- Multi-AZ deployments provide high availability by synchronously (and automatically) replicating the primary database to a standby replica

- Supported Engines: MySQL, PostgreSQL, MariaDB, Oracle, SQL Server, Amazon Aurora
- High Availability: Multi-AZ deployments for automatic failover
- Scalability: Read replicas for horizontal scaling of read workloads
- Backup and Restore: Automated backups, manual snapshots, and point-in-time recovery
- Monitoring: Metrics with Amazon CloudWatch, Performance Insights, and Enhanced Monitoring
- Security: VPC, security groups, encryption at rest and in transit, IAM database authentication
- Pricing: Understand instance classes, storage options (General Purpose SSD, Provisioned IOPS)
- Aurora Features: Aurora Serverless, distributed storage, fault-tolerant architecture

# Redshift

Fully managed data warehousing service for large-scale analytics. Covers columnar storage, distribution keys, and queries optimized for OLAP

- Used for data warehousing and analytics
    - A central repository of data that pulls from many other sources (e.g., S3, databases, etc.)

- Columnar Storage: Data stored in a columnnar format for faster analytics
- Distribution Styles: Choose between AUTO, EVEN, KEY, or ALL distribution for query optimization
- Sort Keys: Define sort keys for faster querying of specific columns
- Cluster Configuration: Nodes (leader and compute nodes), resizing options (elastic resize, classic resize)
- Spectrum: Query S3 data directly without loading it into Redshift
- Security: VPC support, encryption at rest with AWS KMS, network isolation
- Workload Management: Define queues and allocate resources for effcient query execution
- Backup and Recovery: Automatic backups and point-in-time snapshots

- Columnar Storage: Data stored in a columnnar format for faster analytics
- Distribution Styles: Choose between AUTO, EVEN, KEY, or ALL distribution for query optimization
- Sort Keys: Define sort keys for faster querying of specific columns
- Cluster Configuration: Nodes (leader and compute nodes), resizing options (elastic resize, classic resize)
- Spectrum: Query S3 data directly without loading it into Redshift
- Security: VPC support, encryption at rest with AWS KMS, network isolation
- Workload Management: Define queues and allocate resources for effcient query execution
- Backup and Recovery: Automatic backups and point-in-time snapshots

# DynamoDB

Serverless NoSQL databse designed for high throughput and low-latency applications. Key topics include partition keys, indexes, DynamoDB Streams, and capacity modes

- Non-relational or NoSQL databse
    - Data stored as key/value pairs
    - Massively scalable and highly performant
- Two options for scaling:
    - Auto scaling (provisioned)
    - On-demand (more expensive)
- DynamoDB Accelerator is in-memory caching, delivering 10x performance with microsecond READ latency
    - No re-coding necessary

- Core Concepts: Tables, items, and attributes (NoSQL schema)
- Primary Key Types: Partition key and composite key (partition + sort key)
- Indexes: Local Secondary Index (LSI) and Global Secondary Index (GSI) for faster queries
- Capacity Modes: Provisioned capacity (manual scaling) vs. on-demand capacity
- DynamoDB Streams: Real-time data changes for triggers, analytics, and replication
- DAX (DynamoDB Accelerator): In-memory caching for low-latency read performance
- Transactions: ACID compliance for critical operations
- Backup and Restore: Point-in-time recovery and continuous backups
- Security: Encryption at rest and in transit, IAM roles and policies

# Elasticache

In-memory caching service using Redis or Memcached to reduce database load and improve application speed. Understand use cases like caching, session storage, and Pub/Sub

- In-memory database used for caching and session management
- Used for read-intensive web applications, such as gaming or media streaming

- Engines: Redis and Memcached support for caching
- Scaling: Horizontal scaling with sharding, vertical scaling by resizing nodes
- Cluser Modes: Clustered vs non-clustered Redis setups
- Persistence: Redis features like AOF (Append-Only File) and RDB snapshots
- Use Cases: Caching for faster data retrieval, session storage, Pub/Sub messaging
- Monitoring: Integration with CloudWatch for metrics and alerts
- Security: VPC, encryption in transit and at rest (Redis), Redis AUTH
- High Availability: Multi A-Z with automatic failover for Redis clusters

# Neptune

Fully managed graph database service for storing and querying graph data. Focus on use cases like social networks, fraud detection, and knowledge graphs using Gremlin and SPARQL queries

- Graph database
- Used for social media, fraud detection and recommendation engines

- Graph Models: Supports property graph and RDF graph models
- Query Languages: Gremlin for property graphs, SPARQL for RDF graphs
- Use Cases: Social networks, fraud detection, knowledge graphs, and recommendation engines
- Performance: Low-latency graph traversal with optimized data structures
- Scalability: Horizontal scaling with reader replicas
- Backup and Restore: Automated backups, manual snapshots, and point-in-time recovery
- Security: Encryption in transit and at rest, VPC support, IAM integration
- High Availability: Multi-AZ deployment with automated failover
- Monitoring: Integration with CloudWatch and performance optimization tools

