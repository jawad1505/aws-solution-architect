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
    ![modify EBS](https://github.com/jawad1989/aws-solution-architect/blob/master/EC2/images/6%20-%20EBS.PNG)
