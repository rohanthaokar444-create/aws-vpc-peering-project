# AWS VPC Peering Project

This project demonstrates how to connect two AWS VPCs using VPC Peering.
VPC-A (28.0.0.0/16) has a public subnet connected to the internet through an
Internet Gateway and a private subnet. VPC-B (28.200.0.0/16) has a private
subnet. EC2 instances in all three subnets communicate privately using route
tables and security groups, without going through the internet.

## Architecture
![Architecture](architecture-diagram.jpeg)

## Network Details
| Resource | CIDR |
|---|---|
| VPC-A | 28.0.0.0/16 |
| Public Subnet (VPC-A) | 28.0.1.0/24 |
| Private Subnet A (VPC-A) | 28.0.2.0/24 |
| VPC-B | 28.200.0.0/16 |
| Private Subnet B (VPC-B) | 28.200.1.0/24 |

## What I Built
- 2 VPCs connected using VPC Peering
- Internet Gateway attached to VPC-A
- Public and private subnets with separate route tables
- Security groups for SSH and ICMP
- 3 EC2 instances (1 public, 2 private)

## Steps
1. Created VPC-A and VPC-B
2. Created subnets
3. Attached Internet Gateway to VPC-A
4. Created and accepted the peering connection
5. Configured route tables on both sides
6. Created security groups
7. Launched EC2 instances
8. Tested connectivity using ping and SSH

## Test Results
(EC2 ke baad yahan screenshots add honge)

## What I Learned
- Peering needs routes on both sides
- Private subnets are not directly reachable from the internet
- VPC CIDR ranges must not overlap
