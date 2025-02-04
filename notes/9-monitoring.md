# Monitoring

# CloudWatch

Monitor operational metrics, log events, and trigger alarms for AWS resources and applications

- Used for performance monitoring of applications and resources
    - e.g., CPU, network, disk, GPU utilization
- Alarms are used to send notifications when metrics hit some threshold
- The Unified CloudWatch Agent can send longs AND metrics from EC2 and on-premises servers
    - Required to get memory usage information

- Key Features:
    - Metrics: Collect performance metrics from AWS resources (e.g., EC2, RDS, Lambda)
    - Logs: Centralized storage and real-time monitoring of application and system logs
    - Alarms: Notify and take action based on thresholds for metrics
    - Dashboards: Customizable visualizations of resource metrics and logs
    - EventBridge: Automate actions based on state changes or events in AWS services
    - Synthetics: Monitor application endpoints and APIs using canaries to detect availability issues
    - ServiceLens: Gain end-to-end visibility of application performance with distributed tracing

# CloudTrail

Track user activity and API calls to ensure security and compliance

- Captures user activity and API calls
    - e.g., who created an EC2 instance, who terminated an EC2 instance, who logged into the Console
- CloudTrail logs can be sent to CloudWatch for monitoring and alerting

- Key Features:
    - Event History: Logs all API calls made to AWS services by users, roles, or AWS services
    - Trails: Configure specific logs to monitor regions and services of interest
    - Insights: Detect unusual or potentially malicious activity (e.g., spikes in API activity)
    - Integration: Works with CloudWatch for real-time event monitoring and alerts
    - Compliance: Provides an immutable record for auditing purposes

# AWS Config

Assess, audit, and evaluate the configurations of AWS resources for compliance

- Used to inventory resources and record the configuration/changes

- Key Features:
    - Resource Inventory: Tracks configurations changes for AWS resources
    - Compliance Rules: Enforce governance using prebuilt or custom compliance rules (e.g., ensuring S3 buckets are private)
    - Snapshots: View historical configuration states of resources
    - Remediation: Automate corrections whe a rule violation occurs
    - Integrations: Works with AWS Organizations to manage compliance across multiple accounts

# Best Practices

- Centralise monitoring across multiple accounts using CloudWatch cross-account dashboards and AWS Organisations
- Use CloudTrail Insights and Config Rules to proactively monitor and enforce compliance
- Automate remediation actions through Config, Lambda, or EventBridge rules
- Optimise costs by tailoring monitoring solutions to the criticality of resources and applications
- Regularly review CloudWatch alarms and dashboards to ensure they align wish business needs

