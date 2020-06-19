# Table of Contents
### 1. Cloud Watch
### 2. Cloud Trail
### 3. Enable Cloud Watch in Ec2

#  1. Cloud Watch
   Performance
   * Compute (EC2/Autoscaling groups/ELB/Route 53 Health Check)
   * 5 minutes by default
   *Storage & Content Delivery(EBS Volumes / Storage Gateways/Cloud Front)
   * Cloud Watch with EC2:
    * CPU
    * Network
    * Disk
    * Status Check
 
 # 2. Cloud Trail
   * monitors API calls in AWS
   * is like a CCTV, increases visibility into your activity(user/resource) by recording AWS Console and API calls.
   * You can identify users, accounts, source IP, when were calls made 
   
  # 3. Enable Cloud Watch in Ec2
   * Create a new instance and in () select enable cloud watch monitoring(charged)
   ![CW](https://github.com/jawad1989/aws-solution-architect/blob/master/CloudWatch/images/8%20-%20Cloud%20Watch.PNG)
   
   * Goto Cloud Watch create a new alaram, EC2->Per Insance
   
   ![alarm](https://github.com/jawad1989/aws-solution-architect/blob/master/CloudWatch/images/9%20-Create%20Alarm%20-Step1.PNG)
   
   * check per instance
   
   ![part 10](https://github.com/jawad1989/aws-solution-architect/blob/master/CloudWatch/images/10%20-%20Per%20Instance%20Metric.PNG)
   
   * select CPU metrics
   
   ![cpu metrc](https://github.com/jawad1989/aws-solution-architect/blob/master/CloudWatch/images/11%20-%20cpu%20metrics.PNG)
   
   
   * Create a alarm that runs every minute and checks if CPUUtilizaion is greater or equal to 90 %
   
   ![90Percent](https://github.com/jawad1989/aws-solution-architect/blob/master/CloudWatch/images/12%20-%2090%20percent%20alarm.PNG)
   
   *create sns topic and add email id
   
   ![13](https://github.com/jawad1989/aws-solution-architect/blob/master/CloudWatch/images/13%20-Set%20notification.PNG)
   
   * give name and description
   
   ![14](https://github.com/jawad1989/aws-solution-architect/blob/master/CloudWatch/images/14%20-%20name%20and%20desc.PNG)
   
   * confirm email
   ![15](https://github.com/jawad1989/aws-solution-architect/blob/master/CloudWatch/images/15%20-%20email%20confirmation.PNG)
   
