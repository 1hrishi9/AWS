1. What is Site to Site VPN Connection?
By defaut, instances that you launch into an Amazon VPC cant communicate with your own (remote) network,
You can enable access to your remote network from your VPC by crating an AWS Ste-Site VPN,(Sito Ste VPN) connection, and configuring routing o pass traffic through the connection.

 

 

Example:
1. AWS Datacenter (VPC) to Ofc on premises Dataceter
2. One AWS Datacenter (VPC) to another AwS Datacenter (VPC)

2. What ate the Key Concepts for Site-to-Site VPN Connection?
The following are the key concepts for Site-to-Site VPN:
1. VPN connection: A secure connection betwen your on-premises equipment and your PCs.
2. VPN tunnel: An encrypted link where data can pass from the customer network to or from AWS. Each VPN connection includes two VPN tunnels which you can simultaneously Use for high availibility
3. Customer gateway: An AWS resource which provides information to AWS about your customer
gateway device

4. Customer gateway device: A physical devices or software application on your side of the Site-to-Ste VPN connecton.

5. Target gateway: A genric term for the VPN endpoint on the Amazon side of he Site-to-Site VPN connection

6. Virtual private gateway: virtual private gateway is the VPN endpoint on the Amazon side of
yout St-o-Ste VPN connoction ta can be atached oa single VEC.

7. Transit gateway: A transit hub that can be used te interconnect multiple VPCs and on-premises
networks, and as a VPN endpoint for the Amazon side of the Site-to-Site VPN connection

## Understanding Site-to-Site VPN Connection Limitations?

A Site-to-Site VPN connection has the following limitations
            IPv6 traffic is not supported for VPN connections on a virtual private gateway.
            An AWS VPN connection does not support Path MTU Discovery
In addition, take the following into consideration when you use Site-to-Site VPN.
            When connecting your VPCs to a common on-premises network, we recommend that
            you use non-overlapping CIDR blocks for your networks

## How AWS Site-to-Site VPN works
The below point will describe AWS Site-to-Site VPN works:
Site-o-Site VPN Components: A Site-to-Site VPN connection offers two VPN tunnels between a vitual
private gateway or transit gateway on the AWS side, and a customer gateway (which represents a VPN.
device ) on the remote (on-premise) side

A Site-to-Site VPN connection consists of the following components
‘4 Vetual private gateway: Avital private gateway is the VPN concentrator on the Amazon side
othe Ste-o-Ste VPN connection, You creat a vital pat galenay and attach tothe VPC

from which you wat to create the Sto-o-Sile VPN connection,
            

