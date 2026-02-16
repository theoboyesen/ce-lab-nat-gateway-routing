# NAT Gateway – Private Subnet Internet Access Lab

## Overview
This lab demonstrates how to enable outbound internet access for EC2 instances in a private subnet using an AWS NAT Gateway, while ensuring inbound access from the internet is blocked.

## Architecture
- VPC with public and private subnets
- Internet Gateway attached to VPC
- NAT Gateway deployed in public subnet
- Private route table configured to forward outbound traffic to NAT Gateway
- Bastion host used for secure SSH access

## Why NAT Gateway Is Needed
Private subnets do not have direct access to the internet. A NAT Gateway allows instances in private subnets to:
- Download updates
- Access external APIs
- Reach public AWS services

while preventing inbound connections from the internet.

## Implementation Steps
1. Allocate an Elastic IP
2. Create NAT Gateway in public subnet
3. Update private route table to use NAT Gateway
4. Launch EC2 instance in private subnet
5. Verify outbound connectivity and blocked inbound access

## Testing & Validation
- Outbound access verified using curl to external services
- Inbound access blocked by absence of public IP and security group rules

## Security Considerations
- Private instances have no public IP
- SSH access restricted via bastion host
- Security groups use least-privilege rules
