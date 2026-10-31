
# AWS VPC Peering Mini Project

## Project Overview
This project demonstrates how to establish secure private communication between two Amazon Virtual Private Clouds (VPCs) using VPC Peering.

The implementation uses a bastion host to securely access private EC2 instances and route tables to enable communication between resources across the two VPCs.

## Architecture

- **VPC A:** 10.10.0.0/16
- **VPC B:** 10.20.0.0/16
- **Region:** Asia Pacific (Mumbai) – ap-south-1

### Subnet Configuration

| VPC | Subnet | CIDR | Purpose |
|---|---|---|---|
| VPC A | Public Subnet | 10.10.1.0/24 | Bastion Host |
| VPC A | Private Subnet | 10.10.2.0/24 | App-A |
| VPC B | Private Subnet | 10.20.1.0/24 | App-B |

## AWS Services Used

- Amazon VPC
- Amazon EC2
- VPC Peering
- Internet Gateway
- Route Tables
- Security Groups
- Key Pairs

## Implementation Steps

1. Created two VPCs with non-overlapping CIDR blocks.
2. Created public and private subnets.
3. Attached an Internet Gateway to VPC A.
4. Configured public and private route tables.
5. Created security groups with controlled SSH and ICMP access.
6. Launched three EC2 instances: one bastion host and two private application instances.
7. Established a VPC Peering connection between VPC A and VPC B.
8. Updated route tables to enable communication between the VPCs.
9. Accessed private instances through the bastion host using SSH ProxyJump.

## Validation and Testing

- Verified that communication between App-A and App-B failed before VPC Peering.
- Verified successful ICMP communication from App-A to App-B after configuring peering routes.
- Verified reverse communication from App-B to App-A.
- Successfully accessed App-B through the bastion host using SSH ProxyJump.
- Tested controlled ICMP failure by removing and restoring the relevant security group rule.

## Key Learnings

- VPC and subnet configuration
- Public and private network architecture
- VPC Peering and route table configuration
- Security group rules and network access control
- Bastion host and secure SSH connectivity
- Troubleshooting network connectivity

## Project Documentation

Detailed implementation steps and screenshots are available in the documentation folder.

## Author

Maheshwari Phalke
