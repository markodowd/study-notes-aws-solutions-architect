# Identity and Access Management (IAM)

<hr />

# IAM

- Manage identity & access in single AWS account
- Not using AWS Organisations

# IAM Identity Center

- Centrally manage access over multiple accounts
- Uses AWS Organisations

<hr />

# Users

- Represents an individual with credentials to interact with AWS
- Can have direct permissions assigned via policies
- Each user has a unique name within an AWS account
- Supports programmatic access using access keys and secret keys, or console access with a password
- Can belong to one or more gorups for simplified permissions management

# User Groups

- A collection of IAM users that share the same permissions
- Permissions are assigned to the group via policies, which apply to all members
- Users inherit permissions from the groups they are in
- Simplifies permission management for teams or departments

# Roles

- Assigned to entities like AWS services, applications, or users from another AWS account
- Allow temporary access to resources without using long-term credentials
- Defined with trust relationships specifiying who can assume the role
- Commonly used with services like EC2, Lambda, and cross-account access

# Policies

- Documents that define permissions (allow or deny) for accessing AWS resources
- Written in JSON format and attached to users, groups, or roles
- Types:
    - Managed Policies: Created by AWS or users, reusable across entities
    - Inline Policies: Directly embedded in a single user, group, or role, for specific use cases
- Contain statements specifying actions, resources, and conditions

<hr />

