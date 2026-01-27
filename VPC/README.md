# VPC

(AWS) Virtual Private Cloud (VPC), why it is necessary and how its various components interact to ensure security and organization.

# Key Components and Concepts:

To explain the technical aspects of networking, let's walk through the basics:

- IP Address Range: The size of a VPC is defined by its IP address range (CIDR block). For example, a common range might provide 65,536 available IP addresses.

- Subnets: These are sub-networks created by splitting the VPC’s total IP range into smaller segments for specific projects or tiers (e.g., payments or transactions).

- Internet Gateway: This acts as the main gate for the VPC, allowing communication between the VPC and the internet.

- Public and Private Subnets: A public subnet is directly accessible from the internet via the Internet gateway, while a private subnet is isolated and does not have direct internet access.

- Elastic Load Balancer (ELB): Usually placed in a **public subnet**, the ELB receives external traffic and forwards it to the appropriate applications or instances.

- Route Table: This functions as a router, defining the specific paths that traffic must take to reach its destination within the VPC(specific paths traffic must take to move from the load balancer to applications in private subnets)

- Security Group: A virtual firewall for individual EC2 instances that controls inbound and outbound traffic based on specific ports and IP addresses.

# Advanced Security and Monitoring

- NAT Gateway: Located in the **public subnet**, it allows instances in a private subnet to download resources from the internet while masking their private IP addresses to maintain security.

- NACLs (Network Access Control Lists): These provide security automation by applying rules at the **subnet level** rather than to individual instances (Acts as an extra perimeter defense).

- VPC Flow Logs: A monitoring tool used to record and debug traffic flow within the VPC.