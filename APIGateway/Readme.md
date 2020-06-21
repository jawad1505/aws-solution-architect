Fully Managed service that makes it easy for developers to publish, maintain, monitor and secure APIS at any scale
e.g. doorway in your aws, you can control aws by code

users connect to API GAteway it could point to 
* Lambda
* EC2
* Dynamo DB

Expose HTTPS endpoints
Serverless-ly connect to Lambda & Dynamo DB

# How to confiugre
  * Define an API - Container
  * define resources - URL paths
  * for each resource:
    * select supported http method(verb) - get/post/put/delete
    * set security
    * choose target - EC2/lambda/dynamoDB
  
# How to Deploy
  * uses api gateway domain, by default
  * can use custom domains
  * now supports AWS Certification Manager: free SSL/TLS certs

# API caching:
  * reduce # of calls for endpoints

# Same-Origin Policy:
  * a web browser permits scripts contained in first web page to access data in a second web page, but only if origin is same.
  * to preven Cross Site Scriptin (XSS) attacks.

# CORS:
  * that allows restricted resources(e.g. fonts) on a web page to be requested by another domain outside the domain from which the first resource was served
  * You need to enable cors on API Gateway if you get an error ***origion policy cant be read at the remote resource***
#  





