EBS:
  a developer centric view of deploying an app to AWS
  its free but you pay for underlying instance
  Managed Service, AWS beanstalk handles instance configuration/OS
  just application code is responsilbity of developer
  
  Three architectures:
    1. Single instance: good for dev
    2. LB + ASG: good for product + pre prod
    3. ASG only: good for non web apps in production (workers)
    
  Three Components:
    1. Applications
    2. Application Version: each deployment gets assigned a version
    3. Environment name( dev, test, prod). Namig is free
    
    * you deploy app versions to environments and can proomote app versions to next environment
    * Rollback app version
    * Life cycle
      1. Create app and crate environment
      2. Upload Version
      3. Release to Environments
    
