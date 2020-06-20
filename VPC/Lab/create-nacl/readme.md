# 1. install httpd on Public EC2
* ssh into ec2 and run below commands
```
yum install httpd
chkconfig httpd on
service httpd start
cd /var/www/html/
nano index.html

<html><h1> JAWAD SALEEM </h1></html>
```

* Goto public EC2 ip in browser, you will see the page, becuase this subnet is associated witha default NACL that allows http traffic

# 2. Create a new NACL
* In VPC->NACL
* Create a new NACL ( by default all inbound traffic is denied)
![NEW](https://github.com/jawad1989/aws-solution-architect/blob/master/VPC/Lab/images/12%20-%20NACL.PNG)

* in subnet associations press edit
* select public subnet `10.0.1.0` and save
![SUBNET](https://github.com/jawad1989/aws-solution-architect/blob/master/VPC/Lab/images/13%20-%20nacl%20create.PNG)


* you will see subnet associated
* now if you goto browser and refresh it will fail as this new NACL has no HTTP inbound rule set
* add three INBOUND rules for http/https/ssh
![SUBNET](https://github.com/jawad1989/aws-solution-architect/blob/master/VPC/Lab/images/14%20-%20NACL%20add%20rules.PNG)

* also allow outbound rules for 80/443/1024-65535(ephermal ports)
![ephermal](https://github.com/jawad1989/aws-solution-architect/blob/master/VPC/Lab/images/14%20-%20NACL%20add%20rules%20outbound.PNG)


* Now you will be able to access website in browser

* add (1024 - 65535) in inbound rules as for this new NACL
