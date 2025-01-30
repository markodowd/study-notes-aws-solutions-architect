# Automation and Governance

# CloudFormation

- Infrastructure as Code (IaC), defined in a JSON or YAML template
- Repeatable way to deploy, update and delete resources
- Can be used cross-account and cross-region

- Automates provisioning and management of AWS resources using templates (YAML/JSON)
- Supports stack creation, updates, and deletion in a controlled manner
- Enables staack policies for resource protection
- Drift detection to track manual changes outside CloudFormation
- Nested stacks for modular and reusable templates

# Service Catalog

- An approved catalog of products that developers can use
- Organised into portfolios (e.g., web development, data analysis)

- Allows organisations to create and manage approved AWS resources as predefined product portfolios
- Enforces governance by restricting configurations and resource permissions
- Supports versioning for controlled updates of cloud products
- Integrates with CloudFormation and IAM for access management
- Helps prevent shadow IT by enforcing organisational best practices

# Systems Manager (SSM)

- Manage a fleet of servers at scale
- Commonly used for patching and maintenance
- Parameter Store is used to store configuration information and secrets (unencrypted & encrypted)
    - If you need to rotate secrets, you should use Secrets Managers instead

- Provides a single interface for managing AWS and on-premises resources
- Key components:
    - Run Command: Automate remote management tasks across instances
    - Patch Manager: Automates OS patching across fleets
    - Session Manager: Secure shell access without opening SSH ports
    - State Manager: Enforces configuration compliance
    - Automation: Define and execute workflows for common operational tasks

# Systems Manager Parameter Store

- Stores and manages configuration values and secrets (e.g., database passwords, API keys)
- Supports hierarchical organisation of parameters
- Provides encryption with AWS KMS for secure storage
- Integrates with Lambda, EC2, ECS, and CloudFormation for automation
- Versioning and history tracking for auditing changes

