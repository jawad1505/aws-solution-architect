# 1. Create 2 Ec2 intancer
  * Launch 2 EC2 instances
    1. One in us-east-1d subnet
    2. other in us-west-1e subnet
  * give below bootstrap script change value for both servers like Webserver A and Webserver B
  ```
  #!/bin/bash
yum update -y
yum install httpd -y
service httpd start
chkconfig httpd on
cd /var/www/html
echo "<html><h1> Hi i am Webserver A</h1></html>" > index.html
  ```
 * Optional give tags for both server
 * launch them in your default SG with HTTP on

# 2. Create Classic Load balancer
  * in EC2 Dashboard, select Load Balancer
  * Select Classic LB
  * Name your LB
  * HTTP should b allowed
  * in Assign SG , Assing your default SG
  * Skip Security Settings
  * In Configure Health Check give below values
    * Response Timeout: `2`
    * Interval: `5`
    * Unhealthy threshold: `2`
    * Healthy Threshold: `3`
  * Add your EC2 instances
  * Review and submit
  
    ![LB](https://github.com/jawad1989/aws-solution-architect/blob/master/LoadBalancer/Lab/uploads/1%20-%20Load%20Balancer.PNG)
    
  * In Instance Tab when both of your EC2 instances are in `InService ` state
  * Copy the DNS name `Classic-LB-Jawad-1261712819.us-east-1.elb.amazonaws.com`  and put in browser
  * refresh several times you will see the alternate swtiching between your webserver
  
  
  
  
  
  
  
  
  
  
  
  
  
  
