 
  # 1. Create Application Load Balancer
   * First we need to create a target group
    1. Create a Target Group
      * Type: instance
      * VPC: Default
      * NAME: jawad-TG
      * Healh check 2,3,2,6
      * Add both of your Ec2 instances
      * Review and submit
    2. Create a ALB
     * Give Name: Jawad-ALB
     * Select All Subnets
     * Select Internet Facing
     * Select Default SG
     * Select previously created TG: jawad-TG 
     * Review and submit
     * Copy the DNS name from ALB and paste in browser, refresh and you will see webserver swapping
     
     ![ALB](https://github.com/jawad1989/aws-solution-architect/blob/master/LoadBalancer/Lab/uploads/1%20-%20Load%20Balancer.PNG)
  
  
