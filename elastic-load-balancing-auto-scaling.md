# Elastic Load Balancing (ELB)

- Distributes incoming traffic across multiple targets (e.g, EC2 instances, containers)
- Ensures fault tolerance and high availability
- Operates at various layers of the OSI model (Layer 4 and Layer 7)

## Types of Load Balancers

### Application Load Balancer (ALB)

- Works at Layer 7 (HTTP/HTTPS)
- Supports host-based and path-based routing
- Integrated with AWS WAF (Web Application Firewall)
- Ideal for microservices and container-based architectures

### Network Load Balancer (NLB)

- Works at Layer 4 (TCP/UDP/TLS)
- Handles millions of requests per second with ultra-low latency
- Good for real-time applications or systems requiring static IP addresses

### Classic Load Balancer (CLB)

- Operates at Layer 4 and Layer 7
- Legacy option; limited features compared to ALB and NLB
- Not recommended for new applications

## Key Features

### Health Checks

- Monitors the health of registered targets
- Removes unhealthy targets from the rotation

### Sticky Sessions (Session Affinity)

- Ensures a client is always routed to the same target

### Cross-Zone Load Balancing

- Distributes traffic evenly across all registered targets in all Availability Zones

### SSL/TLS Termination

- Offloads SSL decryption to the load balancer
- Reduces computational overhead on backend instances

### Target Groups

- Group of targets (e.g, EC2 instances) for load balancing
- Required for ALB and NLB

# Auto Scaling

- Automatically adjusts the number of instances to match demand
- Ensures high availability and cost efficiency
- Used with Elastic Load Balancing for seamless scaling

## Key Components

### Auto Scaling Groups (ASGs)

- Collection of EC2 instances managed together
- Specify minimum, maximum, and desired capacity

### Launch Templates/Launch Configurations

- Defined EC2 instance configurations (AMI, instance type, key pair, etc)
- Launch Templates are more flexible and preferred over Launch Configurations

## Scaling Options

### Dynamic Scaling

- Adjusts capacity based on demand
- Policies:
    - Target tracking (e,gm maintain CPU utilization at 50%)
    - Step scaling (adjust in increments)
    - Simple scaling (adjust based on alarms)

### Predictive Scaling

- Uses machine learning to forecast demand
- Prepares capacity in advance

### Manual Scaling

- Adjust the capacity manually as needed

## Scaling Metrics

- Common metrics:
    - CPU Utilization
    - Network I/O
    - Custom metrics via Amazon CloudWatch

## Termination Policies

- Determines which instance to terminate during scaling in
    - Oldest launch configuration
    - Closest to next billing hour
    - Default termination is based on Availability Zone balance

## Health Checks

- Replaces unhealthy instances automatically
- Can use ELB health checks or EC2 status checks

# Integrations Between ELB and Auto Scaling

- ELB directs traffic to healthy instances in the ASG
- Auto Scaling maintains the number of healthy instances behind the ELB
- Both services ensure high availability and scalability of applications

# Additional Considerations

- High Availability and Fault Tolerance
    - Use multiple Availability Zones for both ELB and ASG

- Security
    - Use Security Groups, SSL/TLS, and IAM roles

- Monitoring and Logging
    - Enable AWS CloudWatch for metrics and alarms
    - Use Access Logs for ELB

