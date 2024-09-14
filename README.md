# AWS-VPC-Setup-for-Production-and-Development

This project involves creating two distinct Amazon VPCs—one for production and one for development—with specific subnet, instance, and security configurations, along with a peering connection between them.

Overview

Production Network:
Architecture: 4-tier
Subnets:
3 private: app1, dbcache, db
1 public: web1
Instances: Launched and named after respective subnets.
Internet Access: app1 and dbcache subnets have internet access via NAT Gateway.
Security: Managed Security Groups (SGs) and Network ACLs (NACLs).
Development Network:
Architecture: 2-tier
Subnets:
1 public: web
1 private: db
Instances: Launched and named after respective subnets.
Internet Access: Only the web subnet has internet access.
Connectivity:
Peering Connection: Between prod-vpc and dev-vpc.
DB Subnets: Allowed communication between the db subnets of both VPCs.
Setup Steps
VPC Creation:

Production: 10.10.0.0/16
Development: 20.20.0.0/16
Subnets & Instances:

Production: 4 subnets (1 public, 3 private) with instances launched in each.
Development: 2 subnets (1 public, 1 private) with instances launched in each.
Internet Gateway & NAT Gateway:

Production: Attach IGW, set up NAT Gateway for private subnets.
Development: Attach IGW, only web subnet uses IGW.
Peering Connection:

Create VPC peering between production and development VPCs.
Configure route tables for subnet communication.
Security Configuration:

Configure SGs and NACLs to allow appropriate traffic flows between subnets and VPCs.
Conclusion
This project demonstrates how to set up isolated production and development environments in AWS using VPCs, while enabling secure inter-VPC communication between their database subnets.
