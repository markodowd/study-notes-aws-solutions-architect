# Storage

# S3 (Simple Storage Service)

Scalable object storage with options for versioning, lifecycle management, and storage classes (e.g., Standard, Glacier)

- Inexpensive, unlimited, reliable object storage (think: files, photos, logs, etc.)
- Names must be globally unique; flat hierarchy where folders are emulated
- Works in an "eventually consistent" model
- Storage classes optimize cost by storing data according to frequency of access
- Encryption options are server-side (SSE-S3, SSE-KMS, SSE-C) or client-side
- Versioning, MFA delete and object lock help prevent accidental object deletion
    - Governance and Compliance mode for Object Lock
- Access control: IAM policies, bucket policies and access control lists (ACLs)
    - It's possible to block all public access at the account level
- Presigned URLs grant temporary access to a file
- S3 can be used to host a static website
    - If resources are stored on different domains, CORS needs to be enabled
    - Must be granted FROM the cross-origin server

- Object Storage: Stores data as objects in buckets; ideal for unstrucured data like images, videos, and backups
- Storage Classes: Multiple classes for cost optimization (e.g., Standard, Standard-IA, Intelligent-Tiering, Glacier, Glacier Deep Archieve)
- Lifecycle Policies: Automate transitions between storage classes and data expiration to optimise costs
- Versioning: Keep multiple versions of objects to protect against accidental deletion or overwrites
- Cross-Region Replication (CRR): Automatically replicate objects between buckets in different regions for redundancy
- Encryption: Options for server-side (SSE-S3, SSE-KMS, SSE-C) and client-side encryption
- S3 Access Points: Simplify and control access to shared data for multiple applications
- Event Notifications: Trigger workflows with Amazon EventBridge, Lambda, or SQS when changes occur in S3
- Strong Consistency: Provides read-after-write consistency for PUTS and DELETES

# Elastic File System (EFS)

Fully managed, scalable file storage for Linux-based applications, designed for high availability and throughput

- Storage that can be used by multiple services (EC2, Lambda, on-premises servers, etc.)
- Only pay for what you use (no up-front provisioning)
- Has different storage classes (similar to S3)

- File System for Linux: Fully managed NFS file system for Linux workloads
- Elastic Scaling: Automatically adjusts capacity to match your application's storage needs
- Performance Modes: Choose between General Purpose (low latency) and Max I/O (high throughput)
- Access Modes: Supports shared access from multiple EC2 instances and on-premises servers
- Storage Classes: EFS Standard and EFS Infrequent Access (EFS-IA) for cost optimization
- Integration: Works with AWS services like EC2, Lambda, and Kubernetes (EKS)
- Encryption: Data encryption at rest and in transit for security
- Backup Integration: Native integration with AWS Backup for scheduled and point-in-time backups

# Amazon FSx

Manage file systems optimized for specific workloads, including Windows File Server, Lustre for HPC, and NetAPP ONTAP

- Third-party file systems
- FSx for Windows File Server - built on Windows Server
- FSx for Lustre - high-performance file system

- FSx for Windows File Server: Managed Windows file system with SMB protocol, AD integration, and NTFS
- FSx for Lustre: High-performance file system for machine learning, HPC and big data analytics
- FSx for NetApp ONTAP: NetApp's ONTAP file system for hybrid cloud environments, supporting advanced data management
- Backup and DR: Supports AWS Backup for snapshots and disaster recovery strategies
- Elastic Scaling: Automatically adjusts performance and storage as needed
- Access Protocols: Supports SMB, NFS, and Lustre protocols for different workloads
- Integration with AWS Services: Seamlessly connects with EC2, EKS, and on-premises environments

# Storage Gateway

Hybrid storage solution for integrating on-premesis environments with cloud storage via file, volume, or tape gateways

- Used in a hybrid architecture, to store data in AWS from on-premises
- File Gateway uses NFS and SMB for files; Tape Gateway deals with tape backups
- Volume Gateway (iSCSI)
    - STORED mode (data stored on-prem; AWS for backup)
    - CACHED mode (data stored in AWS; frequently-accessed cached on-prem)

- Hybrid Cloud Storage: Bridges on-premises applications with AWS cloud storage
- File Gateway: Enables local file access backed by S3 for data archiving or hybrid workflows
- Volume Gateway: Presents cloud-backed iSCSI block storage for snapshots and recovery
- Tape Gateway: Replaces physical tape libraries with virtual tapes stored in S3 or Glacier
- Caching: Local caching for low-latency access to frequently used data
- Integration: Works with AWS Backup, S3, and Glacier for streamlined data protection
- Data Transfer: Securely transfers data to AWS using SSL and encryption

# Snow Family

Physical devices for offline data transfer, edge computing, and large-scale migrations when network-based transfers are impractical

- Physical storage devices used to transfer massive amounts of data (Snowcone, Snowball, Snowmobile)

- Snowcone: Ultra-portable device for small-scale edge computing or data migration
- Snowball Edge: Offers storage and edge computing for larger data transfer or loca processing
    - Snowball Edge Storage Optimized: Designed for large-scale data migrations and local storage
    - Snowball Edge Compute Optimized: Includes EC2 instances for running edge workloads
- Snowmobile: Massive data transfer (up to 100 PB) via a secure, truck-mounted storage solution
- Use Cases: Data center migration, disaster recovery, and edge computing in disconnected environments
- Offline and Secure: Data is encrypted during transfer, and the device is tamper-resistant

