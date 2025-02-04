# Security & Compliance

# Shared Responsibility Model

- AWS is responsible for security OF the cloud - Underlying infrastructure that runs AWS services
    - Pysical Security
        - Data center security (access controls, surveillance, redundancy)
        - Disaster recovery, power and cooling
    - Network & Hardware Security
        - Global infrastructure security (AWS regions, AZs, Edge locations)
        - Networking protections (DDoS mitigation, AWS Shield, AWS WAF)
    - Host & Virtualisation Security
        - Patching and maintaining AWS-managed hardware and hypervisors
        - Secure software-defined networking (VPC, Security Groups, NACLs)

- Customer is responsible for security IN the cloud - Securing own applications, data and access config
    - Data Security & Encryption
        - Protecting sensitive data in S3, RDS, DynamoDB, etc
        - Managing encryption (AWS KMS, CloudHSM)
    - Identity & Access Management
        - Configuring IAM roles, users, and permissions
        - Enforcing MFA and least privilege access
    - Application & Workload Security
        - Patching and securing OS and software (for EC2, containers, etc.)
        - Using Security Groups, NACLs, and firewall rules correctly
    - Monitoring & Compliance
        - Enabling logging (CloudTrail, CloudWatch Logs)
        - Performing vulnerability assessments (Inspector, GuardDuty)

# Network & DDoS Protection

- AWS Shield
    - Managed DDoS protection service
    - Shield Standard: Free, automatic protection against common DDoS attacks
    - Shield Advanced: Paid service with enhanced detection, mitigation, and response support (includes AWS WAF integration)

- AWS Web Application Firewall (WAF)
    - Protects against common web exploits (SQL injection, XSS, etc.)
    - Uses rule-based filtering for IPs, bots, and rate limits
    - Can integrate with ALB, API Gateway, and CloudFront

# Encryption & Key Management

- AWS Key Management Service (KMS)
    - Managed service for creating, controlling, and using encryption keys
    - Supports summetric and asymmetric encryption
    - Can integrate with S3, EBS, RDS, and more

- AWS CloudHSM
    - Dedicated hardware security module (HSM) for cryptographic operations
    - Provides customer full control over encryption keys
    - Meets compliance needs like FIPS 140-2 Level 3

- AWS ACM (AWS Certificate Manager)
    - Manages SSL/TLS certificates for secure communications
    - Automates renewal and deployment for services like ELB, CloudFront, and API Gateway

# Secrets & Credential Management

- AWS Secrets Manager
    - Secure storage for credentials, API keys, and other secrets
    - Supports automatic rotation of secrets (e.g., for RDS databases)
    - Integrates with AWS Lambda for custom rotation logic

- AWS Systems Manager Parameter Store
    - Stores configuration data and secrets
    - Can be used as an alternative for Secrets Manager (free for standard parameters)
    - Supports encruption via KMS

# Threat Detection & Compliance Monitoring

- Amazon Macie
    - Uses AI/ML to identify sensitive data (PII, financial data) in S3 buckets
    - Provides dashboards and alerts for compliance risks

- Amazon Inspector
    - Automated vulnerability assessment service for EC2 and container workloads
    - Detects CVEs and security issues in installed packages
    - Supports AWS Systems Manager for remediation

- Amazon GuardDuty
    - Threat detection service using AI/ML to analyze AWS logs (VPC Flow Logs, DNS logs, CloudTrail)
    - Detects unauthorized access, reconnaissance, and malware activity

- AWS Security Hub
    - Centralised dashboard for AWS security services (aggregates GuardDuty, Inspector, Macie, etc.)
    - Provides security score and compliance checks (CIS AWS Benchmark, PCI DSS)

- AWS Detective
    - Investigates and visualises security incidents (works with GuardDuty)
    - Uses machine learning to analyse VPC Flow Logs, CloudTrail logs, and GuardDuty findings

# Configuration & Compliance

- AWS Config
    - Tracks AWS resource configurations and changes over time
    - Helps enforce compliance rules and policies (e.g., S3 bucket encryption)

- AWS Artifact
    - Provides on-demand access to AWS compliance reports (SOC, ISO, PCI, etc.)
    - Helps customers meet audit and regulatory requirements

