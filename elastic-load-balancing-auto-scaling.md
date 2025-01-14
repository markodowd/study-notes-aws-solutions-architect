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

