# AWS VPC Peering Project

Hands-on AWS networking project: VPC peering between two VPCs with public and private EC2 instances.

## Architecture


![Architecture](architecture-diagram.jpeg)



## Network Design
| Resource | Name | CIDR |
|---|---|---|
| VPC | VPC-A | 28.0.0.0/16 |
| Public Subnet | Public-Subnet | 28.0.1.0/24 |
| Private Subnet | Private-Subnet-A | 28.0.2.0/24 |
| VPC | VPC-B | 28.200.0.0/16 |
| Private Subnet | Private-Subnet-B | 28.200.1.0/24 |

Region: Asia Pacific (Mumbai) - ap-south-1

## Components
- 2 VPCs with non-overlapping CIDR blocks
- Internet Gateway (IGW-A) attached to VPC-A
- VPC Peering connection (A-to-B) between VPC-A and VPC-B
- 3 route tables: Public-RT, Private-RT-A, Private-RT-B
- 3 security groups: SG-public, SG-private-A, SG-private-B
- 3 EC2 instances (one public, two private)

## Route Tables
| Route Table | Destination | Target |
|---|---|---|
| Public-RT | 0.0.0.0/0 | IGW-A |
| Public-RT | 28.200.0.0/16 | Peering (A-to-B) |
| Private-RT-A | 28.200.0.0/16 | Peering (A-to-B) |
| Private-RT-B | 28.0.0.0/16 | Peering (A-to-B) |

## Screenshots
### VPCs


![VPCs](screenshots/01-vpcs.png)


### Subnets


![Subnets](screenshots/02-subnets.png)


### Internet Gateway


![IGW](screenshots/03-igw.png)


### Peering Connection


![Peering](screenshots/04-peering-active.png)


### Route Tables


![Route Tables](screenshots/05-route-tables.png)



## What I Learned
- How VPCs, subnets and route tables work together
- Difference between public and private subnets
- How VPC peering needs routes on both sides
- How security groups control SSH and ping traffic

## Author
Rohan Thaokar
