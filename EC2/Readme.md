# TABLE OF CONTENTS
# 1. Launch a simple EC2 Instance
# 2. Security Groups
# 3. EBS(Elastic Block Store)
# 4. EBS Vs Instance Store
# 5. ENI VS ENA VS EFA


# 1. Launch a simple EC2 Instance
  * Craete a new instance
  ![EC2](https://github.com/jawad1989/aws-solution-architect/blob/master/EC2/images/1-Create%20Ec2.PNG)
  * run below commands to update and install apache httpd
  ```
  yum update -y
  yum install httpd -y
  ```
  * Create a html file in /var/www/html directory and start the http service
  ```
   touch index.html
   nano index.html
   service httpd start
   start httpd.service
   chkconfig on
  ```
  * goto browser and type your public IP, you will see the html file
  ![http](https://github.com/jawad1989/aws-solution-architect/blob/master/EC2/images/2%20-%20httpd.PNG)


# 2. Security Groups
  * SG are ***STATEFUL*** if we create a rule for inbound automatically outbound will be created and NACL are ***STATELESS***
  * We can assign more than one SG to our EC2
    ![SG](https://github.com/jawad1989/aws-solution-architect/blob/master/EC2/images/3%20-%20SG.PNG)
  * by default all inbound is block
  * we can block specific IP, insead use NACL
  * we can specify allow rules but not deny rules, can do with NACL


# 3. EBS(Elastic Block Store)
  * Persistent block storage volumes for using with EC2
  * Each EBS is automatically replicated within its Availibility Zone
  * EBS Volume will be in same AZ of EC2
  * 5 Types
    * General Purpose - SSD - Max IOPS 16,000
    * Provisional IOPS - SSD - Max IOPS 64,000
    * Throughut Optimized Hard Disk Drive  - Max IOPS 500
    * Cold Hard Disk Drive - Max IOPS 250
    * Magnetic - Max IOPS 40-200 
  * Create a new EC2 with 4 EBS Volumes
    ![EBS](https://github.com/jawad1989/aws-solution-architect/blob/master/EC2/images/4%20-%20EBS.PNG)
  * Modify the ***st1*** from 500 to 1000 by selecting->Actions->Modify Volume
    ![modify EBS](https://github.com/jawad1989/aws-solution-architect/blob/master/EC2/images/5%20-%20EBS.PNG)
  * Now we have to extend the OS file system on the voume to use newly allocated space
  * Gp2 is the root, modify it to Provisioned IOPS and Iops to 100
  
    ![modify EBS](https://github.com/jawad1989/aws-solution-architect/blob/master/EC2/images/6%20-EBS.PNG)
  
  * To move the EBS to new AZ we have to take a snapshot of it from actions. Once done goto snapshots and from actions create image 
  
  ![create image](https://github.com/jawad1989/aws-solution-architect/blob/master/EC2/images/7-%20Snapshot.PNG)
  
  * Goto AMIs, select the new image and launch, in launch select new subnet (us-east-1a)
  
  ![EC2](https://github.com/jawad1989/aws-solution-architect/blob/master/EC2/images/8%20-%20AMI.PNG)
  ![EC2](https://github.com/jawad1989/aws-solution-architect/blob/master/EC2/images/9%20-%20AMI.PNG)
    
  ### * Move EBS to new Region
    
  ![move to new region](https://github.com/jawad1989/aws-solution-architect/blob/master/EC2/images/10%20-%20Move%20EBS%20to%20new%20Region.PNG)
    
  # EBS Vs Instance Store
   * EBS is by default storage
   * For instance stores root device launced from AMI is an instance store vol created from template stored in S3
   * For EBS root device launced from AMI is an EBS vol created from EBS SnapShot
   * instance store are ephermal - EC2 cant be stopped as they are not persistent like EBS.


# 5. ENI VS ENA VS EFA
### ENI
 Elastic Network interface - Essentially a virtual network card
 * create a management network
 * low budget HA solution
 
### EN
 Enhanced Networking. Uses single root I/O virtualization (SR-IOV) to provide high performance networking capabilities on supported instance types.
  * provides higher bandwidth, higher packer per second(PPS)
  * no additional charges, but EC2 has to support it
  * use where you want good performance
  * two ways for enabling it
    * Elastic Network Adapter(ENA), supports network speed upto 100 Gbps
    * Virtual Function (VF), supports network speed upto 10 Gbps
    
### Elastic Fabric Adapter
 A network device that you can attach to your EC2 instance to accelerate High Performance Computing(HPC) and maching learning applications.
 * EFA can use OS-Bypass (Linux Only), OS bypass enable HPC and machine learning apps to bypass the OS kernel and communicate directly with EFA device
 * Machin Learning (important)
