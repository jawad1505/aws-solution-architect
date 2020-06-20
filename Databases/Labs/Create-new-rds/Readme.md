* Create a new RDS instance
* Give your instance name:jawadxiv
* give a database name:jawad
* Create a new VPC
* Create a new EC2 Instance
  * give bootstrap script
```
#!/bin/bash
yum install httpd php php-mysql -y
cd /var/www/html
wget https://wordpress.org/wordpress-5.1.1.tar.gz
tar -xzf wordpress-5.1.1.tar.gz
cp -r wordpress/* /var/www/html/
rm -rf wordpress
rm -rf wordpress-5.1.1.tar.gz
chmod -R 755 wp-content
chown -R apache:apache wp-content
service httpd start
chkconfig httpd on
```
* Goto SG, update new created `rds-launch-wizard-vps` and in inbound rules create a new 'MYSQL' rule and in source give SG for your EC2

* goto your public url once EC2 is up

* give the database name, user and password for RDS and in host enter the endpoint URL of your RDS

![host](https://github.com/jawad1989/aws-solution-architect/blob/master/Databases/Labs/images/4%20-%20install%20wp.PNG)

* create a wp-config.php file in your EC2 instance
![wpconfig](https://github.com/jawad1989/aws-solution-architect/blob/master/Databases/Labs/images/5%20-%20wp-config.PNG)

* Complete the installation
![wp](https://github.com/jawad1989/aws-solution-architect/blob/master/Databases/Labs/images/6%20-%20wordpress.PNG)

![RDS](https://github.com/jawad1989/aws-solution-architect/blob/master/Databases/Labs/images/2%20-%20RDS.png)
