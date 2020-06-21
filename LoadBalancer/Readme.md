# Application Load Balancer 
  * Intelligent
  * Tesla Mode X
  * Best suited for HTTP/HTTPS traffic 
  * Operate at Layer 7 and are application aware
  * create advanced routing, send request to specific web server
  
# Network Load Balancer
  * Best for Extreme performance is required
  * Operate at Layer 4
  * Handling millions of requests per second

# Classic Load Balancer:
  * Legacy
  * You can LB HTTP/HTTPS apps 
  * You can Use Layer 7 specific features such as X-Forward and sticky Sessions
  * You can use Layer 4 LB for apps that rely purely on TCP protocol
  * Not application aware like ALB
  * 504 Gateways Timeout errors
 
 
# X-Forward For Header
  * User browsing to our website on public Address, User IP4 Address `123.12.1.12`
  * request will land at our Load balancer with IP `10.0.0.20`
  * now LB will goto EC2 where EC2 will log user's IP as LB IP `10.0.0.20` (which we dont want, we want exact user's IP)
  * X-Forwarded For will have the public IP address of user which is `123.12.1.12`

# Sticky Session
  * By default, a Classic Load Balancer routes each request independently to the registered instance with the smallest load. However, you can use the sticky session feature (also known as session affinity), which enables the load balancer to bind a user's session to a specific instance. This ensures that all requests from the user during the session are sent to the same instance.
  
  * You can enable sticky sessions to ALB, but traffic will be routed to Target Group rather individual EC2 instance

# Cross Zone Load Balancing

### With cross load balancing 

The following diagrams demonstrate the effect of cross-zone load balancing. There are two enabled Availability Zones, with two targets in Availability Zone A and eight targets in Availability Zone B. Clients send requests, and Amazon Route 53 responds to each request with the IP address of one of the load balancer nodes. This distributes traffic such that each load balancer node receives 50% of the traffic from the clients. Each load balancer node distributes its share of the traffic across the registered targets in its scope.

If cross-zone load balancing is enabled, each of the 10 targets receives 10% of the traffic. This is because each load balancer node can route its 50% of the client traffic to all 10 targets.

![wocb](https://docs.aws.amazon.com/elasticloadbalancing/latest/userguide/images/cross_zone_load_balancing_enabled.png)

### Without Cross Load Balancing

If cross-zone load balancing is disabled:

* Each of the two targets in Availability Zone A receives 25% of the traffic.

* Each of the eight targets in Availability Zone B receives 6.25% of the traffic.

This is because each load balancer node can route its 50% of the client traffic only to targets in its Availability Zone.
![wcb](https://docs.aws.amazon.com/elasticloadbalancing/latest/userguide/images/cross_zone_load_balancing_disabled.png)

# Path Patterns

You can create a listener with rules to forward requests based on the URL path. This is known as path-based routing. If you are running microservices, you can route traffic to multiple back-end services using path-based routing. 

For example, you can route general requests to one target group and requests to render images to another target group.

***Common Scenario***: you want webserver files to be hosted in one subnet (group of ec2 insances) and images to be in other subnet(group of Ec2 Instancer) you give the path in LAB listner rules for images jawadxiv.com/images

[How to Create a Path Pattern](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/tutorial-load-balancer-routing.html)
