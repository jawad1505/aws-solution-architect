

# 1. What is VPC

![vpc](https://github.com/jawad1989/aws-solution-architect/blob/master/VPC/images/2%20-%20VPC.png)

![VPC](https://github.com/jawad1989/aws-solution-architect/blob/master/VPC/images/1%20-%20what%20is%20VPC.PNG)

# 2. Subnet
 AWS reserves 5 subnet addresses from your pool
 
# 3. IGW
  One IGW per VPC

# 4. NAT instances & NAT Gateways
 * NAT instance is a single EC2 instance that we use in our private subnet 
 * NAT Gateway is a highly available Gateway that allows your private subnets to communicate to outer world e.g. downloading files
 
 [Disable Source/Destination Checks](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_NAT_Instance.html#EIP_Disable_SrcDestCheck)


# 5. Access Control List
* NACL can have many subnets
* but one subnet can have one NACL
* Rule with lower range will have a higher priority e.g. 100 > 200 > 300 so on
* NACL comes before Security group 
* NACL can block IPs, SG cant
* NACL are stateless; SG are stateful

# 6. Load Balancer
You need two subnets with Internet gateway to create a ALB

# 7. VPC flowLogs
* feature that enables you to capture information about IP traffic going to and from your network interface in your VPC.
* flow log data is stored using cloud watch
* can be craeted at 3 levels
 1. VPC
 2. Subnet
 3. Network Interface Level

# 8. Bastian Host
A bastion host is a special-purpose computer on a network specifically designed and configured to withstand attacks. The computer generally hosts a single application, for example a proxy server, and all other services are removed or limited to reduce the threat to the computer.

# 9. Direct Connect
dedicated solution to establish a dedicated connection from on premise to AWS.
private connection

# 10. Global Accelerator:
* A service in which you craete accelerators to improve availability and performance of your apps for local and global user.
* directs trafficto optimal endpoints over the AWS global network. This improves availability/performance of your internet apps 
* 2 static IPs by default 

![ga](https://d1.awsstatic.com/r2018/b/ubiquity/global-accelerator-how-it-works.feb297eb78d8cc55205874a1691e0ea2bc8bdbf1.png)

# 11. VPC Endpoint

A VPC endpoint enables you to privately connect your VPC to supported AWS services and VPC endpoint services powered by AWS PrivateLink without requiring an internet gateway, NAT device, VPN connection, or AWS Direct Connect connection. Instances in your VPC do not require public IP addresses to communicate with resources in the service. Traffic between your VPC and the other service does not leave the Amazon network.

Endpoints are virtual device

There are two types of VPC endpoints: interface endpoints and gateway endpoints. Create the type of VPC endpoint required by the supported service.


An interface endpoint is an elastic network interface with a private IP address from the IP address range of your subnet that serves as an entry point for traffic destined to a supported service


A gateway endpoint is a gateway that you specify as a target for a route in your route table for traffic destined to a supported AWS service. The following AWS services are supported:

  Amazon S3

  DynamoDB

# Questions

*  By default, any user-created VPC subnet WILL NOT automatically assign public IPv4 addresses to instances – the only subnet that does this is the “default” VPC subnets automatically created by AWS in your account.

* Each subnet must reside entirely within one Availability Zone and cannot span zones.

* In a custom VPC with new subnets in each AZ, there is a route that supports communication across all subnets/AZs. Plus a default SG with an allow rule 'All traffic, all protocols, all ports, from anything using this default SG'. 

* An application load balancer must be deployed into at least two subnets.

* A Bastion host allows you to securely administer (via SSH or RDP) an EC2 instance located in a private subnet. Don't confuse Bastions and NATs, which allow outside traffic to reach an instance in a private subnet.

* As transitive peering is not allowed, VPC 'B' can communicate directly only with VPC 'A'.

* Security Groups are stateful and Network Access Control Lists are stateless.

* 5 VPC are allowed in a region by default
