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
wget https://wordpress.org/latest.tar.gz
tar -xzf latest.tar.gz
cp -r wordpress/* /var/www/html
rm -rf wordpress
rm -rf latest.tar.gz
chmod -R 755 wp-content
chown -R apache:apache wp-content
chkconfifg httpd on
service httpd start
```

![RDS](https://github.com/jawad1989/aws-solution-architect/blob/master/Databases/Labs/images/2%20-%20RDS.png)
