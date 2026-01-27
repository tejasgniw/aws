# High-Level AWS VPC Architecture Diagram

                           🌐 INTERNET
                                |
                                |
                       +------------------+
                       | Internet Gateway |
                       +------------------+
                                |
                -----------------------------------
                |                                 |
        🟢 Public Subnet A                 🟢 Public Subnet B
        (AZ-1)                             (AZ-2)
                |                                 |
        +------------------+              +------------------+
        |  ELB / ALB / NLB |              |  ELB / ALB / NLB |
        +------------------+              +------------------+
                |                                 |
                |                                 |
        +------------------+              +------------------+
        |  NAT Gateway     |              |  NAT Gateway     |
        +------------------+              +------------------+
                |                                 |
                |                                 |
        -----------------------------------------------------
        |                                                   |
 🔵 Private Subnet A                               🔵 Private Subnet B
 (AZ-1)                                           (AZ-2)
        |                                                   |
 +------------------+                            +------------------+
 | EC2 / EKS / App  |                            | EC2 / EKS / App  |
 | Security Group   |                            | Security Group   |
 +------------------+                            +------------------+
        |                                                   |
        -----------------------------------------------------
                                |
                         Internal AWS Services
                        (RDS, ElastiCache, S3*)

- S3 is accessed via VPC Endpoint, not NAT (best practice)


# How traffic flows

## Incoming Internet Traffic (Users → App)

User → Internet Gateway → ELB (Public Subnet)
     → Route Table → EC2/EKS (Private Subnet)


## Outgoing Internet Traffic (App → Internet)

EC2 (Private Subnet)
 → Route Table (0.0.0.0/0 → NAT Gateway)
 → NAT Gateway (Public Subnet)
 → Internet Gateway → Internet
