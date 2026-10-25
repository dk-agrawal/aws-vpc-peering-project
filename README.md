# AWS VPC Peering Project

## Project Overview
This project demonstrates secure private communication between two Amazon Virtual Private Clouds (VPCs) using AWS VPC Peering.

## Architecture

- **VPC A:** `10.10.0.0/16`
- **VPC B:** `10.20.0.0/16`
- **Bastion Host:** `10.10.1.10`
- **Application Server A:** `10.10.2.10`
- **Application Server B:** `10.20.1.10`

## AWS Services Used
- Amazon VPC
- EC2 Instances
- VPC Peering
- Route Tables
- Internet Gateway
- Security Groups
- Amazon Linux 2023

## Implementation
1. Created two VPCs with non-overlapping IPv4 CIDR ranges.
2. Configured public and private subnets.
3. Created and configured security groups.
4. Launched a public Bastion host and two private application instances.
5. Created and activated a VPC Peering connection.
6. Added routes to enable private communication between both VPCs.
7. Tested connectivity using ICMP ping and SSH.
8. Temporarily removed an inbound ICMP rule to verify traffic blocking.
9. Restored the security rule and verified connectivity again.

## Test Results

- App-A to App-B: Successful.
- App-B to App-A: Successful.
- Controlled ICMP blocking test: 100% packet loss while the inbound ICMP rule was removed.
- Connectivity after restoring the rule: Successful.

## Screenshots
See the `screenshots/` directory for evidence of the peering connection, routing configuration, connectivity tests, and controlled failure test.

## Security Notes
- Application instances have no public IPv4 addresses.
- SSH access is restricted through the Bastion host.
- Private keys and AWS credentials are not included in this repository.

## Cleanup
AWS resources should be deleted when the lab is no longer required to avoid unnecessary charges.

**Note:** Resource names and IP addresses document the lab configuration. AWS resources may no longer be active after cleanup.
