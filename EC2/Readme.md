# TABLE OF CONTENTS
### 1. Launch a simple EC2 Instance
### 2. Security Groups
### 3. EBS(Elastic Block Store)
### 4. EBS Vs Instance Store
### 5. ENI VS ENA VS EFA
### 6. Encrypted Root Device Vol & Snapshots
### 7. Using IAM roles with EC2
### 8. Create BootStrap Scripts for EC2
### 9. EC2 instance Meta Data

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


# 6. Encrypted Root Device Vol & Snapshots
Create an EC2 instance with no encryption on EBS, then create a snap shot, from that snap shot create a encrypted snapshot and use this to launch a new AMI which will be encrypted

* Goto Volumes and See your unencrypted volume
 
 ![EBS UE](https://github.com/jawad1989/aws-solution-architect/blob/master/EC2/images/1-%20UnEncrypted.PNG)
 
* Goto Actions and create an unecryped snapshot

![UE snap](https://github.com/jawad1989/aws-solution-architect/blob/master/EC2/images/2%20-%20Snap.PNG)

* Goto Snapshots and copy and check encryption

![Enc](https://github.com/jawad1989/aws-solution-architect/blob/master/EC2/images/3%20-%20Encrypted.PNG)

* you can see the encryption done
![done](https://github.com/jawad1989/aws-solution-architect/blob/master/EC2/images/4%20-%20Encrypted%20Done.PNG)

* Create an Image(AMI) from the snapshot
![encrypted](https://github.com/jawad1989/aws-solution-architect/blob/master/EC2/images/5%20Encrypted%20AMI.PNG)

* Goto AMI and you will see the new image, launch an EC2 instance from this. 
![AMI](https://github.com/jawad1989/aws-solution-architect/blob/master/EC2/images/6%20-%20Live%20AMI.PNG)

![AMI](https://github.com/jawad1989/aws-solution-architect/blob/master/EC2/images/7%20-%20Create%20EC2%20from%20aMI.PNG)


# 7. Using IAM roles with EC2
 * e,g, you had 1000 Ec2 instance and you were not using role and access key id and secret key was lost,  you have to create new ones and update on each EC2, however if you had roles you can access all of them
 * in this lab we will create a new role with full Administrative Access(Policy) and name it AdminAccess
 * SSH into a machine where you have given only programtic access to user
 ```
 ssh ec2-usre@<PUBIC_IP> -i private_key.pen
 
 remove the $HOME/.aws folder
 cd ~
 rm -rf .aws
 
 run aws s3 ls 
 
 you will get an error sayig no permission, you can re configure by using aws configure
 ```
 
 * Then we will create a new EC2 instance and goto action and press `Attach/Replace IAM Role`
 ![iam](https://github.com/jawad1989/aws-solution-architect/blob/master/EC2/images/1%20-%20Atach%20Iam%20role.PNG)
 
 * This will give our EC2 user full access
 ![roles](https://github.com/jawad1989/aws-solution-architect/blob/master/EC2/images/1-%20IAM%20Role.PNG)
 
 * now SSH into EC2 
 ```
 run aws s3 ls
 ```
 
 * you will be able to access everything


# 8. Create BootStrap Scripts for EC2
* Launch a new EC2
* Select a role with AdminAccess
* in bootstrap script paste below code
this will install `httpd` service, create an index.html file in `html` directory, create a S3 Bucket and copy that index.html into new S3 Bucket
```
#!/bin/bash
yum update -y
yum install httpd -y
service httpd start
chkconfig httpd on
cd /var/www/html
echo "<html><h1>Hello Jawad Saleem Welcome To My Webpage</h1></html>"  >  index.html
aws s3 mb s3://random123123sdasdasd
aws s3 cp index.html s3://random123123sdasdasd
```
![bootstrap](https://github.com/jawad1989/aws-solution-architect/blob/master/EC2/images/3-%20Bootstrap.PNG)

* once instance is up and running, you can paste your public ip in browser and verify your page, also goto s3 and see the new bucket with your index.html 
![s3](https://github.com/jawad1989/aws-solution-architect/blob/master/EC2/images/4-%20Bucket%20Created.PNG)


# 9. EC2 instance Meta Data
 you can view your instance meta data by ssh into your EC2 instance ad type below commands
 ```
 sudo su
 curl http://169.254.169.254/latest/user-data

```

* get list of what you can see

```
curl http://169.254.169.254/latest/meta-data


ami-id
ami-launch-index
ami-manifest-path
block-device-mapping/
events/
hibernation/
hostname
iam/
identity-credentials/
instance-action
instance-id
instance-type
local-hostname
local-ipv4
mac
metrics/
network/
placement/
profile
public-hostname
public-ipv4
public-keys/
reservation-id
security-groups
```

* then pass at end of URL

```
curl http://169.254.169.254/latest/meta-data/instance-id
i-0e45c6aaec247058d
```

* you can save this to a file on start up if you want to save something in db or s3
```
curl http://169.254.169.254/latest/user-data > bootstrap.txt
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100   270  100   270    0     0  54000      0 --:--:-- --:--:-- --:--:-- 54000
[root@ip-172-31-63-189 ec2-user]# cat bootstrap.txt
#!/bin/bash
yum update -y
yum install httpd -y
service httpd start
chkconfig httpd on
cd /var/www/html
echo "<html><h1>Hello Jawad Saleem Welcome To My Webpage</h1></html>"  >  index.html
aws s3 mb s3://random123123sdasdasd
aws s3 cp index.html s3://random123123sdasdasd[
 ```
