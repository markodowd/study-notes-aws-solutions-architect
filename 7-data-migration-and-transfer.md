# Database Migration and Transfer

# Database Migration Service (DMS)

Migrate databases to AWS with minimal downtime

- Used to migrate databses from on-premises to AWS, AWS to AWS, or AWS to on-premesis
- Supports homogeneous (same databse engines) or heterogeneous (different database engines)
    - For heterogeneous, use the Schema Conversion Tool

- Supported Sources Relational databases, NoSQL databases, and data warehouses
- Key Features:
    - Homogeneous (e.g., Oracle to Oracle) and heterogeneous (e.g., SQL Server to Aurora) migrations
    - Supports continuous data replication for real-time syncing
    - Schema conversion with AWS Schema Conversion Tool (SCT)

# DataSync

Automate and accelerate data transfer between on-premisees storage and AWS

- Used to transfer large amounts of data from on-premesis to AWS, AWS to AWS, or other cloud providers to AWS
    - DataSync agent installed at the source
    - On a schedule, data is transferred to DataSync in AWS, and then copied to the AWS destination service (S3, EFS, FSx)

- Supported Sources/Destinations: NFS, SMB, Amazon S3, Amazon EEFS, FSx, and more
- Key Features:
    - Incremental and parallel data transfer
    - Built-in data validation to ensure accuracy
    - Integration with CloudWatch for monitoring

# Application Migration Service (MGN)

Simplify the lift-and-shift migration of applications to AWS

- Used for lift-and-shift migrations from on-premises to AWS
- Replaces the Server Migration Service (SMS)

- Key Features:
    - Agent-based migration with automated server replication
    - Supports any-to-AWS migration (e.g., VMware, Hyper-V, and physical servers)
    - Minimal downtime and continuous testing in the target environment

# AWS Transfer Family

Enable secure file transfer protocols into and out of AWS (e.g., SFTP, FTPS, and FTP)

- Used to transfer files over FTP to either S3 or EFS

- Key Features:
    - Fully managed service supporting Amazon S3 and EFS as backends
    - Custom domain and identity provider integration
    - Encryption in transit and at rest

# AWS Snow Family

Physically transfer large data volumes to AWS when network-based transfer isn't practical

- Physical devices used to transfer data from on-premises to AWS
- Snowcone, Snowball, Snowmobile (a semi-truck)

- Services in the Family:
    - Snowcone: Small and portable device for edge computing and data transfer (up to 8TB)
    - Snowball Edge: Larger, rugged devices for petabyte-scale data migration and edge processing
    - Snowmobile: Exabyte-scale data transfer via a shipping container
- Key Features:
    - Secure, tamper-resistant devices
    - Encryption using AWS Key Management System (KMS)

