# Build a VPC

![VPC](https://github.com/jawad1989/aws-solution-architect/blob/master/VPC/Lab/images/6%20-%20VPC.PNG)

### 1. Create your VPC - CIDR 10.0.0.0/16 NAME:jawadxiv
   When you create a VPC, by default below things will be created
    * Route table
    * NACL
    * Security Group
    
 ![vpc](https://github.com/jawad1989/aws-solution-architect/blob/master/VPC/Lab/images/3%20-%20Create.PNG)
  
 ### 2. Create 2 subnet
   1. Subnet 1:
      * CIDR: 10.0.1.0/24
      * NAME: 10.0.1.0 - us-east-1a
      * VPC:  jawadxiv
      * Once created, Click Actions->Modify/Assing Public IP address and check it
      
   2. Subnet :
      * CIDR: 10.0.2.0/24
      * NAME: 10.0.2.0 - us-east-1b
      * VPC:  jawadxiv
   
 ### 3. Create IGW
   * Create a new IGW with Name "jawad-IGW"
   * Modify and Attach to VPC "jawadxiv"
   
### 4. Create a Route Table
  * Create a new Route Table with Name "public-routeTable-jawadxiv"
  * Attach to our VPC "jawadxiv"
  * Edit routes
    * Add Route with Destination: "0.0.0.0/0"  and IGW: "jawad-IGW"
    ![pubic](https://github.com/jawad1989/aws-solution-architect/blob/master/VPC/Lab/images/4%20-%20public%20subnet.PNG)
    
  * In `Subnet Associations` Edit it
    * Add Public Subnet "10.0.1.0 - us-east-1a" 
    * this will remove the Public Subnet from default Route Table

### 5. Create 2 EC2 instances
  One in public Subnet other in private subnet
  
  1. Public EC2
      * Select VPC `jawadxiv` 
      * Select Subnet `10.0.1.0 - us-east-1a`
      * Create a new SG `jawadxiv-SG` add http allow all traffic `0.0.0.0/0`
    
  2. Private EC2
      * Select VPC `jawadxiv`
      * Select Subnet `10.0.2.0 - us-east-1b`
      * Select Default SG 
    
  * Goto your VPC `jawadxiv` and enable DNS hostnames
  ![hostname](https://github.com/jawad1989/aws-solution-architect/blob/master/VPC/Lab/images/5%20-%20Enable%20DNS.PNG)
  
### 6. Create a SG for private EC2
   * Create a New Security Group for private EC2
   * Name: My_DB_SG
   * Add rules `HTTP/ICMP/HTTPS/SSH` so Public EC2 can access this
   ![sg](https://github.com/jawad1989/aws-solution-architect/blob/master/VPC/Lab/images/7%20-%20Db%20SG.PNG)
   
   * Now Goto Private EC2 - and assignt his new SG 
   
### 7. SSH private from public
 * SSH into public Ec2 and ping Private EC2 (private IP) to test  if its accessible
