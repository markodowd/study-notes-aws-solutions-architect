# The Well-Architected Framework and Cloud Adoption Framework (CAF)

# Six Pillars of AWS Well-Architected Framework

## Operational Excellence

- Perform operations as code
    - CloudFormation
- Make frequent, small, reversible changes
    - Small changes are easier to reverse if needed
- Refine operations procedures frequently
    - Set up regular time to review and validate procedures
- Anticipate failure
    - Identify and mitigate potential failures early and often
- Learn from operational failures
    - Identify lessons learned, and share them

- Automate operations as code
- Document and refine processes
- Anticipate failure and design for observability

## Security

- Implement a strong identity foundation
    - Principle of least privilege: separation of duties
- Enable traceability
    - Monitor, alert and audit
- Apply security at all layers
    - NACLs, security groups, applications, etc.
- Automate security best practices
- Protect ata in transit and at rest
- Keep people away from data
- Prepare for security events

- Implement identity and access management (IAM)
- Enable encryption and data protection
- Automate security best practices

## Reliability

- Automatically recover from failure
    - Monitor for performance and act (e.g., CloudWatch alarms, Load Balaners and Auto Scaling Groups)
- Test recovery procedures
    - Check backup/recovery of S3, EBS, EFS
- Scale horizontally
    - Distribute load across multiple small resources rather than one large resource
- Stop guessing capacity
    - Monitor performance and scale resources out/in, and/or go serverless
- Manage change in automation
    - Changes should be tracked and reviewed (e.g., CloudFormation)

- Design systems for failure recovery
- Ensure reliable workload performance
- Implement distributed system design

## Performance Efficiency

- Democratise advanced technologies
    - Outsource complex tasks to AWS
- Go global in minutes
    - Deploy across multiple regions to provide lower latency and a better user experience
- Use serverless architectures
    - Let AWS manage the underlying infrastructure (e.g., Lambda, Fargate)
- Experiment more often
    - Test different types/configurations of compute and storage to find the optimal solution
- Consider mechanical sympathy
    - Choose a solution that aligns to workloads goals (e.g., EC2 instance types)

- Use a data-driven approach for scaling
- Select the right AWS services for workload optimisation
- Continuously review and evolve

## Cost Optimisation

- Implement cloud financial management
    - Invest time across the organisation to understand/manage finances
- Adopt a consumption model
    - Get in the mindset of paying for what you use: shut things down when you don't need them
- Measure overall efficiency
    - What gets measured gets done
- Stop spending money on undifferentiated heavy lifting
    - Let AWS do things like data center operations so you can focus on your business
- Analyse and attribute expenditure
    - Dig into the details of resource costs

- Implement cost-aware architecture
- Use pricing models efficiently (e.g., Spot, Reserved Instances)
- Monitor and optimise spending

## Sustainability

- Understand your impact
    - Measure the impact of your workloads
- Establish sustainability goals
- Maximise utilisation
    - Right-size workloads
- Anticipate and adopt new, more efficient offerings
- Use managed services
- Reduce downstream impact of your workloads

- Reduce environmental impact of cloud workloads
- Optimise resource usage and efficiency
- Use AWS's shared responsibility model for sustainability

# Cloud Adoption Framework (CAF)

Provides guidance for organisations moving to the cloud

## Six CAF Perspectives
    1. Business Perspective
        - Align cloud strategy with business goals
        - Measure ROI and track business outcomes
    2. People Perspective
        - Define roles and skills needed for cloud adoption
        - Enable workforce training and change management
    3. Governance Perspective
        - Establish cloud policies and compliance frameworks
        - Manage risk and decision-making processes
    4. Platform Perspective
        - Define cloud architecture and best practices
        - Standardise tools and services for cloud deployment
    5. Security Perspective
        - Implement cybersecurity best practices
        - Ensure compliance and risk management
    6. Operations Perspective
        - Optimise IT service management (ITSM)
        - Establish monitoring, automation, and incident response

