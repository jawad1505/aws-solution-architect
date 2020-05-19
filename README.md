# aws-solution-architect

# IAM
* Centarlized Control of your AWS account
* Shared Acccess to your AWS account
* Granular Permissions
* Identity Federation (including Active Directory, Facebook, LinkedIn etc)
* Multifactor Authentication
* Provide Temporary Access for users/devices and services where necessary* 
* Allows you to set up your own password rotation policy
* Integrates with many different AWS services
* Supports PCI DSS framework

### Key Terminologies
* Users
  people, employees
* Groups
  collection of users, each user will inherit permission of group
* Policies
  made up of documents called policy documents. JSON format, and they give permissions as to what user/group/role is able to do.
* Roles
  You create roles and assign them to AWS Resources

### LAB
* Enable MFA
* Customize URL
* Create a new User
  * Create Group (Policy: Administrator Access)
* Apply an IAM Password Policy
* Roles (Give S3 accesss to EC2)
