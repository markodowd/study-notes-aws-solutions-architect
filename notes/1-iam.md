# Identity and Access Management (IAM)

# IAM

- Manage identity & access in single AWS account
- Not using AWS Organisations

- Root account has permission to do everything, including access to billing info
  - Do NOT use it for everyday work; use an IAM user instead
- By default, IAM users have no permissions
- Multi-factor authentication (MFA) can and should be enforced for the root account and individual users
- Access keys are required for programmatic access (CLI, SDK)
- Roles should be used to give permission to other AWS services
- Permissions are controlled by policies; give least privileges
- If a permission isn't given, then by default, it is denied
- If two policies are in place, the most restrictive one "wins"

# IAM Identity Center

- Centrally manage access over multiple accounts
- Uses AWS Organisations

# Core Concepts

- IAM Users and Groups: Entities representing individual users and collections of users for streamlined access control
- IAM Roles: Temporary permissions for trusted entities to access AWS resources
- IAM Policies: JSON documents defining granular access permissions for AWS resources

# Users

- Represents an individual with credentials to interact with AWS
- Can have direct permissions assigned via policies
- Each user has a unique name within an AWS account
- Supports programmatic access using access keys and secret keys, or console access with a password
- Can belong to one or more groups for simplified permissions management

- Users: Represent individuals; each has a unique name and credentials (passwords or access keys)

# User Groups

- A collection of IAM users that share the same permissions
- Permissions are assigned to the group via policies, which apply to all members
- Users inherit permissions from the groups they are in
- Simplifies permission management for teams or departments

- Groups: Collections of users with shared permissions to simplify management
- Best Practice: Assign permissions to groups rather than individual users

# Roles

- Assigned to entities like AWS services, applications, or users from another AWS account
- Allow temporary access to resources without using long-term credentials
- Defined with trust relationships specifiying who can assume the role
- Commonly used with services like EC2, Lambda, and cross-account access

- Grant temporary access to AWS resources for trusted entities like users, applications, or services
- Common Use Cases:
  - Cross-Account Access: Allow entities in one account to access resources in another
  - Service Roles: Grant AWS services (e.g., EC2, Lambda) permissions to perform actions
  - Federated Access: Assign roles to users authenticated via external identity providers

# Policies

- Documents that define permissions (allow or deny) for accessing AWS resources
- Written in JSON format and attached to users, groups, or roles
- Types:
  - Managed Policies: Created by AWS or users, reusable across entities
  - Inline Policies: Directly embedded in a single user, group, or role, for specific use cases
- Contain statements specifying actions, resources, and conditions

- JSON-based permissions that define allowed/denied actions on resources
- Types of Policies:
  - Managed Policies: AWS-managed or customer-managed reusable policies
  - Inline Policies: Policies directly attached to a specific user, group or role
- Structure Components:
  - Effect: Allow or Deny
  - Action: Specific operations (e.g., s3:PutObject)
  - Resources: Resources (e.g., ARN) the action applies to

# Access Management

- Access Keys: Credentials for programmatic access via AWS CLI or SDKs
- Multi-Factor Authentication (MFA): Enhanced security for AWS accounts using additional authentication factors
- Permission Boundaries: Limits to the maximum permissions an IAM entity can have

- Access Keys:
  - Credentials for CLI or API access, consisting of an access key ID and secret access key
  - Best Practice: Rotate keys regularly and use them only when necessary
- Multi-Factor Authentication (MFA):
  - Enhances security by requiring a one-time code from an authenticator app or hardware token
  - Supported for root accounts, IAM users, and AWS SSO users
- Permission Boundaries:
  - Define maximum permissions an entity can have, regardless of additional permissions granted
  - Useful for limiting permissions for roles or users with delegated administration

# Authentication and Integration Tools

- Security Token Service
  - Used to grant temporary credentials to AWS (such as with AssumeRole)
- Cognito
  - Recommended way to manage users for mobile and web-based applications
- Managed Microsoft AD
  - Controls how Microsoft technologies (SharePoint, .NET, SQL Server) in a VPC interact with AWS resources
- AD Connector
  - A proxy to on-premises Active Directory; all users managed on-premises
- AWS SSO
  - Allows users to log in only once, and credentials are used across accounts and other applications
- Organizations
  - A collection of accounts; required to use SSO
  - Service Control Policies (SCP) let you define allow/deny for an entire account

# Authentication

- AWS Single Sign-On (SSO): Centralized user authentication for AWS and third-party applications
- Federated Access: External identity providers (e.g., SAML, OpenID Connect) for accessing AWS resources
- Cognito User Pools and Identity Pools: Tools for managing user authentication and app-level authorization

- AWS Single Sign-On (SSO):
  - Centralized identity management for AWS accounts and applications
  - Supports integration with external identity providers like Microsoft Active Directory or Okta
- Federated Access:
  - Allows users to sign in using external identity providers
  - Supports protocols like SAML 2.0 and OpenID Connect
  - Useful for corporate users needing access to AWS without creating separate IAM users
- Cognito User Pools and Identity Pools:
  - User Pools: Manage sign-up/sign-in for app users, with built-in user directories
  - Identity Pools: Grant temporary access to AWS resources based on user identity
  - Supports social sign-in (Google, Facebook) and enterprise identity providers

# Advanced IAM Features

- Service Control Policies (SCPs): Organisation-wide permissions to control account-level access in AWS Organizations
- Resource-Based Policies: Policies attached directly to resources like S3 buckets and Lambda functions

- Service Control Policies (SCPs):
  - Set guardrails at the organizational or account level in AWS Organisations
  - Prevent actions even if IAM policies allow them
  - Example: Restrict creating certain resource types accross all accounts
- Resource-Based Policies:
  - Attach directly to resources like S3 buckets, Lambda functions, or KMS keys
  - Can include cross-account access and condition keys for fine-grained control

# Integration Tools

- AWS STS (Security Token Service): Temporary security tokens for limited-time resource access
- IAM Identity Center: Unified access across multiple AWS account and services
- AWS Directory Service: Integration with Active Directory for seamless authentication

- AWS STS (Security Token Service):
  - Issues temporary, limited-privilege credentials for users or applications
  - Commmon Use Cases:
    - Enabling cross-account or federated access
    - Temporary access for mobile or browser-based apps
- IAM Identity Center:
  - Centralized user management and permission for accessing multiple AWS accounts
  - Integrates with external identity providers for seamless authentication
- AWS Directory Service:
  - Fully managed Microsft Active Directory or AD Connector for AWS
  - Allows seamless integration with on-premises directories for authentication and resource access
