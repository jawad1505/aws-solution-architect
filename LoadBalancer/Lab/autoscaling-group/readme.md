# 1. Create A Launch Confiugration
* Goto AutoScaling Group in Ec2 Console
* BootStrap Script
```
#!/bin/bash
yum update -y
yum install httpd -y
service httpd start
chkconfig httpd on
cd /var/www/html
echo "<html><h1>Welcome to the EC2 AutoScaling Group</h1></html>" > index.html
```
* Create a new AutoScaling GRoup and follow below steps

![as](https://github.com/jawad1989/aws-solution-architect/blob/master/LoadBalancer/Lab/uploads/1%20-%20AS.PNG)
![as](https://github.com/jawad1989/aws-solution-architect/blob/master/LoadBalancer/Lab/uploads/2%20-%20AS.PNG)
![as](https://github.com/jawad1989/aws-solution-architect/blob/master/LoadBalancer/Lab/uploads/3-b-AS.PNG)


# 2. Create an AutoScaling Group

![as](https://github.com/jawad1989/aws-solution-architect/blob/master/LoadBalancer/Lab/uploads/4-AG.PNG)
![as](https://github.com/jawad1989/aws-solution-architect/blob/master/LoadBalancer/Lab/uploads/5-A.PNG)
![as](https://github.com/jawad1989/aws-solution-architect/blob/master/LoadBalancer/Lab/uploads/6-AG.PNG)
![as](https://github.com/jawad1989/aws-solution-architect/blob/master/LoadBalancer/Lab/uploads/7-AG.PNG)
![ag](https://github.com/jawad1989/aws-solution-architect/blob/master/LoadBalancer/Lab/uploads/8-AG.PNG)
![ag](https://github.com/jawad1989/aws-solution-architect/blob/master/LoadBalancer/Lab/uploads/9-AG.PNG)
![ag](https://github.com/jawad1989/aws-solution-architect/blob/master/LoadBalancer/Readme.md)
