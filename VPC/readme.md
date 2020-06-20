

# 1. What is VPC

![vpc](https://github.com/jawad1989/aws-solution-architect/blob/master/VPC/images/2%20-%20VPC.png)

![VPC](https://github.com/jawad1989/aws-solution-architect/blob/master/VPC/images/1%20-%20what%20is%20VPC.PNG)

# 2. Subnet
 AWS reserves 5 subnet addresses from your pool
 
# 3. IGW
  One IGW per VPC

# NAT instances & NAT Gateways
 NAT instance is a single EC2 instance that we use in our private subnet 
 NAT Gateway is a highly available Gateway that allows your private subnets to communicate to outer world e.g. downloading files
 
 [Disable Source/Destination Checks](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_NAT_Instance.html#EIP_Disable_SrcDestCheck)
