# Elastic Compute Cloud (EC2)

- Provides virtual servers (instances) to run applications
- Highly configureable: Choose instance types, operating systems, and storage
- Offers various purchasing options:
    - On-Demand: Pay-as-you-go, no upfront commitment
    - Reserved Instances: Discounted rates for long-term commitments
    - Spot Instances: Spare capacity at reduced prices, but interruptible
- Scalable: Can auto-scale up or down based on demand using Auto Scaling Groups
- Integration with Elastic Load Balancing for high availability
- Requires managing infrastructure like patching, scaling, and backups

# AWS Elastic Beanstalk

- A Platform as a Service (PaaS) for deploying and managing applications
- Supports multiple programming languages and platforms (Java, Python, Node.js, etc.)
- Simplifies deployment by handling provisioning, load-balancing, scaling, and monitoring
- Developers can focus on code; infrastructure management is abstracted
- Provides flexibility to customize resources if needed (e.g., underlying EC2 instances)
- Ideal for web applications and services with moderate complexitiy

# AWS Lambda

- A serverless compute service that runs code in response to events
- No need to manage infrastructure; scales automatically
- Billed only for execution time and memory used
- Ideal for event-driven architectures (e,g., file uploads to S3, API calls, database changes)
- Supports multiple languages (Node.js, Python, Go, Java, etc.)
- Best suited for microservices, automation tasks, and lightweight workloads
- Constrained by execution time (15-minute limit) and resource limits

# AWS Containers

## Amazon ECS (Elastic Container Service)

- Fully managed container orchestration service
- Supports Docker containers and integrates with IAM, VPC, and monitoring services
- Works with EC2 or Fargate (serverless compute for containers)

## Amazon EKS (Elastic Kubernetes Service)

- Managed Kubernetes service for deploying, scaling, and managing containerized applications
- Offers more flexibility than ECS for users familiar with Kubernetes
- Integrates with AWS services like IAM, CloudWatch, and ALB

## AWS Fargate

- Serverless compute engine for containers
- Works with ECS or EKS to eliminate infrastructure management
- Automatically scales container instances as needed
- Ideal for running containers without worrying about managing EC2 instances

