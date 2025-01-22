# Networking

# Virtual Private Cloud (VPC)

Core networking construct allowing isolated virtual networks in AWS, including subnets, route tables, and internet gateways

- Your own private cloud/network within the cloud that isolates your resources
- Split into subnets:
    - Public: has a route to an Internet Gateway
    - Private: does NOT have a route to an Internet Gateway; if  you need to access the internet, use a NAT Gateway
- VPCs are tied to a region and span multiple availability zones
- IP Addressing
    - For CIDR blocks, the higher the network mask (the "slash number"), the fewer addresses available
        - e.g /32 is a single IP address; /16 is 65,536 IP addresses
    - RFC 1918 addressing is for private addresses
        - Common ranges for AWS work are 172.* and 10.*
- Route tables control the flow of traffic between different resources
- VPC endpoints allow you to access other AWS resources over the private AWS network (rather than the internet)
    - "Gateway" type endpoints are for S3 and DynamoDB
    - "Interface" type endpoints are for all other services
- VPC Flow Logs give visibility into all network traffic (VPC level, subnet level, security group level, etc.)

- Provides an isolated virtual network environment in AWS
- Subnets: Divide the VPC into public and private segments for better resource organization and security
- Route Tables: Direct traffic within the VPC and to external networks like the internet or on-premises environments
- Internet Gateway (IGW): Allows resources in public subnets to access the internet
- Egress-Only Internet Gateway: For IPv6 traffic to access the internet without inbound connections
- Peering Connections: Directly connect two VPCs for resource sharing
- VPC Endpoints: Connect VPC to AWS services without traversing the public internet

# Network Security

Access Control Lists (ACLs) provide stateless traffic filtering at the subnet level for inbound and outbound network traffic

- Network access control lists (ACLs) control traffic at the subnet level; stateless
- Security Groups control traffix at the EC2 instance level; stateful

- Stateless firewalls applied at the subnet level
- Inbound and Outbound rules: Specify allowed or denied traffic based on IP ranges, protocols, and ports
- Rule evaluation occurs in a sequential order (lowest to highest rule number)
- Complementary to Security Groups, which operate at the instance level
- Common use cases: Block specific IP ranges, implement subnet-level restrictions

# Elastic Network Interfaces (ENIs)

Virtual network interfaces that can be attached to instances, enabling advanced networking setups like failover and IP management

- A virtual network card
- All EC2 instances (or their ENIs) have private IP; can optionally have a public IP and Elastic (fixed, public) IP

- A network interface that can be attached to EC2 instances
- Suppoprts multiple private IP addresses, public IP addresses, and Elastic IPs
- Can be detached from one instance and attached to another, useful for high availability and failover scenarios
- Enables advanced configurations like dual-homed instances and static IP addresses
- Used with Network Load Balancers and application failovers

# Network Address Translation (NAT)

Enables private instances to access the internet while keeping them secure by hiding their IP addresses

- Translates a private address to a public address
- Can be performed by: Internet Gateway, NAT Gateway and NAT Instance (no longer supported)
- Bastion hosts can be used in a publix subnet to allow SSH-ing into an instance in a private subnet (a "jump host")

- Facilitates outbound internet access for resources in private subnets
- NAT Gateway: AWS-managed service that offers high availability and scalability
- NAT Instance: A user-managed EC2 instance used for NAT, with more manual setup and maintainance
- Difference with IGW: NAT only allows outbound traffic, while IGW supports both inbound and outbound
- Best practice: Place NAT Gateways in multiple Availability Zones for redundancy

# Hybrid Networking

Solutions like VPN and AWS Direct Connect allow integration of on-premises networks with AWS environments securely and efficiently

- Site-to-Site VPN
    - Traffic is encrypted, but flows over the Internet
    - Inexpensive and easy to set up
- Direct Connect
    - A dedicated physical connection (i.e. bypasses the Internet
    - Data not encrypted by default
    - Faster performance, but takes longer to set up

- VPN: Secure, encrypted connection between on-premises environments and AWS over the internet
    - Supports Site-to-Site and Client VPN options
    - Easy to set up but may have bandwidth limitations due to the internet backbone
- AWS Direct Connect: Dedicated, private network connection from on-premises to AWS
    - Provides low latency and high bandwidth connections
    - Suitable for enterprise workloads and data transfer-heavy applications
- Transit Gateway: Centralized hub for interconnecting multiple VPCs and on-premises networks
- Route 53: DNS service that facilitates domain management and hybrid routing configurations
- Customer Gateways and Virtual Private Gateways: Components required for setting up VPN connections to AWS

