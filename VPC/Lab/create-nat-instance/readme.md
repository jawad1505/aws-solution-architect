##  1. Createa a EC2 - NAT instance

* Goto EC2 Services
* Launch Wizard
* Select Community AMI
* Search NAT and select first one
* Select your VPC `jawadxiv'
* select public subnet
* select public SG
* Launch

## 2. Disable Source/Destination checks
Each EC2 instance performs source/destination checks by default. This means that the instance must be the source or destination of any traffic it sends or receives. However, a NAT instance must be able to send and receive traffic when the source or destination is not itself. Therefore, you must disable source/destination checks on the NAT instance.

You can disable the SrcDestCheck attribute for a NAT instance that's either running or stopped using the console or the command line.

To disable source/destination checking using the console

* Open the Amazon EC2 console at https://console.aws.amazon.com/ec2/.

* In the navigation pane, choose Instances.

* Select the NAT instance, choose Actions, Networking, Change Source/Dest. Check.

* For the NAT instance, verify that this attribute is disabled. Otherwise, choose Yes, Disable.

* If the NAT instance has a secondary network interface, choose it from Network interfaces on the Description tab and choose the interface ID to go to the network interfaces page. Choose Actions, Change Source/Dest. Check, disable the setting, and choose Save.
