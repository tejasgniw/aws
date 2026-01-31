# AWS Networking & Security Q&A

## 1. Designing a Two-Tier Architecture
**Question:** How do you design a highly available and scalable VPC architecture for a two-tier application?  
**Answer:**  
- Create public and private subnets across multiple Availability Zones for high availability.  
- Place the load balancer in the public subnet and application servers in the private subnet.  
- Use Auto Scaling Groups to handle scalability by automatically adjusting the number of instances based on demand.

## 2. Restricting Outbound Internet Access
**Question:** How can you restrict outbound internet access for one subnet while allowing it for another?  
**Answer:**
- Modify the route table associated with the subnet that connects to the IGW. 
- To block internet access, remove the default route (`0.0.0.0/0`) that points to the Internet Gateway.  
- Without this route, traffic cannot flow to the external internet.
- In case of no IGW, there is no access to the external world or the other way around.

## 3. Internet Access for Private Subnets
**Question:** How do instances in a private subnet securely access the internet for software updates?  
**Answer:**  
- Use a NAT (Network address translation) Gateway (or NAT instance) placed in the public subnet. (Masks the private IP address)
- Configure the private subnet’s route table to send outbound traffic to the NAT Gateway.  
- This allows outbound communication while keeping instances' private IPs hidden from the internet.

## 4. Private IP Communication
**Question:** What steps are needed to allow two EC2 instances to communicate using private IP addresses?  
**Answer:**  
- Instances should ideally be in the same VPC and subnet to share the same CIDR block.  
- If in different VPCs, implement **VPC Peering**, updating route tables to allow communication through the VPC link.

## 5. Implementing Strict Network Control
**Question:** How do you achieve fine-grained network access control?  
**Answer:**  
- Use **Network ACLs (NACLs)**.  
- Security Groups provide instance-level security; NACLs provide subnet-level control, allowing explicit allow/deny rules for IPs.

## 6. Creating Isolated Environments
**Question:** How do you set up an isolated environment within a VPC for sensitive workloads?  
**Answer:**  
- Create a dedicated private subnet with no route to an Internet Gateway. (Or no IGW)
- Ensures workloads are not reachable from the internet and have no outbound internet access.

## 7. Secure Communication with AWS Services
**Question:** How can instances within a VPC communicate securely with services like S3 or DynamoDB?  
**Answer:**  
- Use **VPC Endpoints** to connect privately to AWS services without traffic going over the public internet.

## 8. Security Groups vs. NACLs
**Question:** What is the primary difference between a Security Group and a Network ACL (NACL)?  
**Answer:**  
- **Security Groups:** Instance-level, stateful (automatically allows return traffic).  
- **NACLs:** Subnet-level, stateless (both inbound and outbound rules must be defined manually).

## 9. IAM Components (Users, Groups, Roles, Policies)
**Question:** What are the differences between IAM users, groups, roles, and policies?  
**Answer:**  
- **Users:** Unique identities for individuals.  
- **Policies:** JSON documents defining permissions (authorization).  
- **Groups:** Collections of users; updating a group policy affects all users.  
- **Roles:** Identities used by AWS services (e.g., EC2) to perform actions without permanent credentials.

## 10. Administrative Access to Private Instances
**Question:** How do you securely access instances in a private subnet for administrative tasks?  
**Answer:**  
- Deploy a **Bastion Host (Jump Server)** in the public subnet.  
- Log into the Bastion Host first, then use it to connect to private instances via SSH (Linux) or RDP (Windows).
