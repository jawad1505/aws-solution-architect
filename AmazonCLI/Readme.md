### 1. Create an IAM user programmatic access only
  * Create a new user in IAM
  * give programmatic access only
  * create a group and assign AdministratorAccess policy
  * Download the keys
  
### 2. Create an EC2 instance 
  * create a new key pair and download it

### 3. ssh into EC2
  * goto the directory which has your keypair pem file 
  * open a terminate and type below commands
  ```
  ssh ec2-user@35.174.207.32 -i CliTest.pem
  sudo su
  
  aws s3 ls 
  ```
  * you will not be shown anything, now you have to login the AWS using the new user credentials(Access key and Secret)
  ```
  aws configure
  
  will ask for 
  Access ID:  <YOUR_ACCESS_ID>
  Secret Access key:  <YOUR_SECRET_ACCESS_KEY>
  Regsion: us-east_1
  Default Output format: 
  
  aws s3 ls
  
  aws s3 mb s3://myTestNewBucketJawad1989
  
  aws s3 ls
  
  ```
  
  * you will see the bucket will be created and you will be able to access it, to view your credentials
  ```
  cd ~
  cd .AWS
  ls
  
  cat credential
  ```
