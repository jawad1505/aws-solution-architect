# Summary:
  1. User goes to domain gets ip address
  2. use ip to access S3 web page static with a button
  3. presses a button goes to API Gateway to get dynamic content
  4. API gateway proxies Lambda to pull content

Steps:
  1. Create Function
  2. Name: jawad-lambda-hello-world
  3. RunTime: Python 3.6
  4. Role: Create new role myLambdaRole
  5. Policy Template: Simple microservice permission
  6. Desinger:
    1. Add Triggers:
      * 
    2. Function Code:(IDE)
      * Add code 
      * Save
    3. Environment Variables:
    4. Tags
    5. Execution Role
    6. Basic Settings:
      * Description: My lambda function
    7. Network
    8 . Debuggin and Error Handling
    9. Concurrency
    10. Auditing and Complaince 
