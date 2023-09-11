# VPC

==========================================================================================================================

🌐 Navigating AWS VPC Limits 🚀

In the ever-expanding universe of Amazon Web Services (AWS), your Virtual Private Cloud (VPC) serves as the foundation for network architecture. However, it's crucial to understand the limits and quotas that AWS sets to ensure your VPC operates seamlessly. Let's explore these boundaries! 🛰️

💫VPC and subnets

🚫VPCs per Region - Default = 05 (Adjustable = Yes)
You can increase this limit so that you can have hundreds of VPCs per Region.
🚫Subnets per VPC - Default = 200 (Adjustable = Yes)
🚫IPv4 CIDR blocks per VPC - Default = 05 (Adjustable up to 50)
🚫IPv6 CIDR blocks per VPC - Default = 05 (Adjustable up to 50)

♻️Elastic IP addresses
🚫Elastic IP addresses per Region - Default = 05 (Adjustable = Yes)
This quota applies to individual AWS account VPCs and shared VPCs.
🚫Elastic IP addresses per public NAT gateway - Default = 02 (Adjustable = Yes)

♻️Gateways
🚫Egress-only internet gateways per Region - Default = 05 (Adjustable = Yes)
🚫Internet gateways per Region - Default = 05 (Adjustable = Yes)
🚫NAT gateways per Availability Zone - Default = 05 (Adjustable = Yes)
🚫Private IP address quota per NAT gateway - Default = 08 (Adjustable = Yes)
🚫Carrier gateways per VPC - Default = 01 (Adjustable = NO)

♻️Network ACLs
🚫Network ACLs per VPC - Default = 200 (Adjustable = Yes)
🚫Rules per network ACL - Default = 20 (Adjustable = Yes)

♻️Network interfaces
🚫Network interfaces per instance - Default = Varies by instance type (Adjustable = No)
🚫Network interfaces per Region - Default = 5000 (Adjustable = Yes)

♻️Route tables
🚫Route tables per VPC - Default = 200 (Adjustable = Yes)

♻️Security groups
🚫VPC security groups per Region - Default = 2500 (Adjustable = Yes)
🚫Inbound or outbound rules per security group - Default = 60 (Adjustable = Yes)
🚫Security groups per network interface - Default = 05 (Adjustable up to 16)

♻️VPC peering connections
🚫Active VPC peering connections per VPC - Default = 50 (Adjustable up to 125)


♻️VPC endpoints
🚫Gateway VPC endpoints per Region - Default = 20 (Adjustable = Yes)
🚫Interface and Gateway Load Balancer endpoints per VPC - Default = 50 (Adjustable = Yes)

♻️Network Address Usage
🚫Network Address Usage - Default = 64,000 (Adjustable up to 256,000)