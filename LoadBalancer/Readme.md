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
