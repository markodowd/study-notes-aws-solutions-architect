# DNS and Network Routing

# Route 53

Route 53 is a scalable and highly available DNS web service

- Managed domain name service (DNS)
- Used to map IP addresses (142.251.215.238) to domain names (google.com)
- Can register domain names (mywebsite.com)
- Used to route traffic ACROSS regions using various routing policies
    - Can be used in combination with elastic load balancers (which route traffic only in a single region)
- DNS record types
    - A Record: Points a host name to a specific IP address (aws.amazon.com -> 205.251.242.103)
    - CNAME: Points a host name to another name or A Record (amznwebsvcs.mywebsite.com -> aws.amazon.com)
    - Alias: Specific to AWS; points a host name to an AWS resource, such as an S3 static website or a CloudFront distribution

- Key Features:
    - Domain Registration: Register and manage domain names directly through Route 53
    - DNS Routing Policies:
        - Simple, Weighted, Latency-Based, Geolocation, Geoproximity, Multi-Value Answer, and Failover
    - Health Checks: Monitor application endpoints and route traffic based on health
    - Traffic Flow: Create advanced routing policies using a visual editor
    - Integration with AWS Services: Route traffic to resources like EC2, S3, ELB

- Use Cases:
    - Load balancing across multiple regions
    - Disaster recovery setups

# CloudFront

CloudFront is a globally distributed content delivery network (CDN)

- Content delivery network (CDN) that's geographically distributed to deliver content faster by caching
- Commonly used to deliver media files (videos, images)
- Can be used in conjunction with Route 53

- Key Features:
    - Edge Locations: Serve content with low latency using over 400 edge locations globally
    - Origin Servers: Distribute content from AWS resources (e.g., S3, EC2) or external HTTP servers
    - Caching: Reduce latency and improve performance with caching at edge locations
    - Security Features:
        - HTTPS support and custom SSL certificates
        - Integration with AWS WAF for web application protection
    - Dynamic and Static Content: Efficiently deliver both dynamic and static assets

- Use Cases:
    - Accelerating website performance
    - Reducing load on origin servers

# Global Accelerator

Global Accelerator improves the performance of global applications by directing user traffic through AWS's global network

- Uses global network of edge locations to improve speeds for a variety of applications
- Does not use caching; improvement comes from network routing of traffic (moving off the public internet)

- Key Features:
    - Static IP Addresses: Use two static IPs as fixed entry points for applications
    - Anycast Routing: Automatically routes traffic to the closest healthy endpoint
    - Health Checks: Actively monitors endpoint health and reroutes traffic as needed
    - Integrations: Works with resources like EC2, ALB, and NLB
    - Failover Support: Ensures high availability with automatic failover

- Use Cases:
    - Latency-sensitive applications
    - High availability and disaster recovery

# Best Practices

- Use Route 53 for intelligent DNS routing and failover
- Leverage CloudFront for caching static and dynamic assets to reduce latency
- Incorporate Global Accelerator for improving network performance and resilience for global users
- Combine these services to build a scalable, reliable, and efficient architecture

