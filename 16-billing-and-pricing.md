# Billing & Pricing

# AWS Pricing Models

- Pay-as-you-go: Pay only for what you use, no upfront costs
- Savings Plans: Commitment-based pricing for cost reduction (Compute & EC2 Instance Savings Plans)
- Reserved Instances (RIs): Up to 75% discount for long-term EC2, RDS, Redshift, and ElastiCache usage
- Spot Instances: Up to 90% discount on unused EC2 capacity, but instances can be terminated anytime
- Dedicated Hosts: Physical servers reseerved for regulatory or licensing needs
- Free tier: Includes always-free (e.g., Lambda 1M requests/month), 12-month free services, and trial-based offers

# Pricing Plans For EC2

- On-demand is the easiest, but most expensive
- Spot instances allow you to bid on excess capacity (up to 90% savings), but instances can be terminated at any time
- Reserved offers 30-60% savings for reservations of 1-3 years for a specific instance type
- Savings Plans combine on-demand and reserved. You receive saving on the commitment of spend for 1-3 years and then get on-demand pricing after that
    - EC2 Savings Plan: Applies only to EC2 Instances
    - Compute Savings Plan: Applies to EC2, Lambda and Fargate

- On-Demand: Pay per second/minute/hour, no commitment
- Reserved Instances (RI): 1 or 3 year term, discounts based on payment model (All Upfront, Partial Upfront, No Upfront)
- Spot Instances: Bidding system with low-cost compute but risk of termination
- Savings Plans: Flexible usage-based commitment for consistent workloads
- Dedicated Hosts/Instances: Physical server reservations with hourly billing

# AWS Organizations

Manage multiple accounts centrally

- Organisations are a collection of accounts
- Enable consolidated billing (costs for all accounts roll up into a single bill)
- Can share discounted pricing across accounts

- Consolidated Billing
    - Single payment method for multiple linked accounts
    - Volume discounts for aggregated usage
    - Cost separation via linked accounts
- Service Control Policies (SCPs): Governance over accounts

# Cost Allocation Tags

- Once activated, can be used to group and filter charges (such as "createdBy")

- User-defined & AWS-generated tags: Assign metadata to resources for cost tracking
- Used in Cost Explorer & AWS Budgets: Helps categorise spending by department, project, or environment
- Must be activated in the AWS Billing Console

# Billing Dashboard

- Provides a snapshot of costs by service, forecasted costs, etc.

- Central view of costs & usage trends
- Displays estimated charges and billing reports
- Provides quick access to Cost Explorer, Budgets, and payment settings

# Cost Explorer

- Provides a way to drill into specific charges and group/filter by service, region, tags, etc.
- Can provide a forecast of charges based on existing usage

- Visual tool for nalyzing AWS spending trends
- Supports filtering by service, region, linked account, and cost allocation tags
- Forecasting feature predicts future costs based on past usage
- Granular breakdown of usage & costs

# AWS Pricing Calculator

- Prior iterations were called the "Total Cost of Ownership" (TCO) Calculator and the "Simple Monthly Calculator"
- Publicly available at calculator.aws
- Provides an estimate of costs based on the services chosen (useful for existing customers, as well as those who are evaluating AWS)

- Estimates monthly costs for AWS services before deployment
- Customizable based on expected usage
- Includes EC2 instance comparisons, data transfer estimations, and Reserved Instance savings analysis

# AWS Budgets

- Create and track budgets and send alerts
- Alerts can be based on actual AND forecasted spend
- Can filter alarms by region and service
- Budgets can be created for cost, usage, Savings Plans and Reservations

- Set custom cost & usage thresholds
- Receive notifications via email or SNS when budget is exceeded
- Supports RI and Savings Plan utilization tracking
- Allows setting forecast-based alerts

# CloudWatch Billing Alerts/Alarms

- Activated through Billing (not through CloudWatch)
- More limited than Budgets; only used to send alerts
- Alerts can only be based on actual spend (NOT forecasted)
- Filtering by region is not possible

- CloudWatch alarms for unexpected billing increases
- Triggered based on predefined budget thresholds
- Can send notifications via SNS to alert users about spending spikes
- Helps prevent overuse & unexpected charges

