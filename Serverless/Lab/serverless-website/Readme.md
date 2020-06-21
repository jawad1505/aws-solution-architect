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

# Website Code:
 [Code](https://github.com/jawad1989/aws-solution-architect/tree/master/Serverless/Lab/uploads/original(1))
 
# steps in Images:
![aws](https://github.com/jawad1989/aws-solution-architect/blob/master/Serverless/Lab/uploads/1%20-%20Lambda.PNG)

![aws](https://github.com/jawad1989/aws-solution-architect/blob/master/Serverless/Lab/uploads/2%20-%20Click%20here.PNG)

![aws](https://github.com/jawad1989/aws-solution-architect/blob/master/Serverless/Lab/uploads/3%20-%20Delete%20This.PNG)

![aws](https://github.com/jawad1989/aws-solution-architect/blob/master/Serverless/Lab/uploads/4-%20Create%20new%20method.PNG)

![aws](https://github.com/jawad1989/aws-solution-architect/blob/master/Serverless/Lab/uploads/5%20-Deploy%20API.PNG)

![aws](https://github.com/jawad1989/aws-solution-architect/blob/master/Serverless/Lab/uploads/6%20-%20Get%20URL.PNG)

![aws](https://github.com/jawad1989/aws-solution-architect/blob/master/Serverless/Lab/uploads/7%20-%20URL.PNG)

![aws](https://github.com/jawad1989/aws-solution-architect/blob/master/Serverless/Lab/uploads/8%20-%20S3%20Create%20bucket.PNG)

![aws](https://github.com/jawad1989/aws-solution-architect/blob/master/Serverless/Lab/uploads/9%20-%20S3%20Static%20Hosting.PNG)

![aws](https://github.com/jawad1989/aws-solution-architect/blob/master/Serverless/Lab/uploads/10%20-%20make%20objects%20public.PNG)

![aws](https://github.com/jawad1989/aws-solution-architect/blob/master/Serverless/Lab/uploads/11%20-%20Upload%20files.PNG)

![aws](https://github.com/jawad1989/aws-solution-architect/blob/master/Serverless/Lab/uploads/12%20-%20Click%20Me.PNG)

![aws](https://github.com/jawad1989/aws-solution-architect/blob/master/Serverless/Lab/uploads/13%20-%20Route%2053.PNG)

