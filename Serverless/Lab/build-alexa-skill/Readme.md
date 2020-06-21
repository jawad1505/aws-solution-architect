# Amazon Echo:


# Amazon Alexa
Amazon Alexa, also known simply as Alexa, is a virtual assistant AI technology developed by Amazon, first used in the Amazon Echo smart speakers developed by Amazon Lab126

* When u talk to Echo-> Goes to Alexa - > calls Lamdbda function

# Lab
  1. Create a S3 Bucket
  2. Give Permission->Bucket Policy, change the ARN
  
```
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadGetObject",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "ARN here/*"
    }
  ]
  }
```
  3. Goto Amazon Poly Service
    
  # Steps in images
  
![alexa](https://github.com/jawad1989/aws-solution-architect/blob/master/Serverless/Lab/uploads/alexa/0%20-%20create%20s3.PNG)

![alexa](https://github.com/jawad1989/aws-solution-architect/blob/master/Serverless/Lab/uploads/alexa/0%20-%20c%20bucket%20policy.PNG)

![alexa](https://github.com/jawad1989/aws-solution-architect/blob/master/Serverless/Lab/uploads/alexa/1%20-%20Create%20Polly.PNG)

![alexa](https://github.com/jawad1989/aws-solution-architect/blob/master/Serverless/Lab/uploads/alexa/2%20-%20Synthesize%20to%20S3.PNG)

![alexa](https://github.com/jawad1989/aws-solution-architect/blob/master/Serverless/Lab/uploads/alexa/3%20-%20Task%20Created.PNG)

![alexa](https://github.com/jawad1989/aws-solution-architect/blob/master/Serverless/Lab/uploads/alexa/4%20-See%20Tasks.PNG)

![alexa](https://github.com/jawad1989/aws-solution-architect/blob/master/Serverless/Lab/uploads/alexa/5%20-%20s3%20will%20have%20that%20file.PNG)

![alexa](https://github.com/jawad1989/aws-solution-architect/blob/master/Serverless/Lab/uploads/alexa/6%20-%20Create%20Lambda%20Function.PNG)

![alexa](https://github.com/jawad1989/aws-solution-architect/blob/master/Serverless/Lab/uploads/alexa/7%20-%20Deploy.PNG)

![alexa](https://github.com/jawad1989/aws-solution-architect/blob/master/Serverless/Lab/uploads/alexa/8%20-%20Lambda%20Dashboard.PNG)

![alexa](https://github.com/jawad1989/aws-solution-architect/blob/master/Serverless/Lab/uploads/alexa/9%20-%20Add%20Fact%20to%20Code.PNG)

![alexa](https://github.com/jawad1989/aws-solution-architect/blob/master/Serverless/Lab/uploads/alexa/10%20-%20Copy%20ARN.PNG)

![alexa](https://github.com/jawad1989/aws-solution-architect/blob/master/Serverless/Lab/uploads/alexa/11%20-%20Alexa%20Developer%20-%20Add%20Skill.PNG)

![alexa](https://github.com/jawad1989/aws-solution-architect/blob/master/Serverless/Lab/uploads/alexa/12-%20%20Skill.PNG)

![alexa](https://github.com/jawad1989/aws-solution-architect/blob/master/Serverless/Lab/uploads/alexa/13%20-%20Fact%20Skill.PNG)

![alexa](https://github.com/jawad1989/aws-solution-architect/blob/master/Serverless/Lab/uploads/alexa/14%20-%20Developer%20Console.PNG)

![alexa](https://github.com/jawad1989/aws-solution-architect/blob/master/Serverless/Lab/uploads/alexa/15-%20Paste%20ARN%20in%20endpoint.PNG)

![alexa](https://github.com/jawad1989/aws-solution-architect/blob/master/Serverless/Lab/uploads/alexa/16%20-%20Add%20Fact.PNG)

![alexa](https://github.com/jawad1989/aws-solution-architect/blob/master/Serverless/Lab/uploads/alexa/17%20-%20Build%20Model.PNG)

![alexa](https://github.com/jawad1989/aws-solution-architect/blob/master/Serverless/Lab/uploads/alexa/18%20-%20Test%20Development.PNG)

![alexa](https://github.com/jawad1989/aws-solution-architect/blob/master/Serverless/Lab/uploads/alexa/19%20-%20Copy%20Paste%20your%20bucket%20file%20to%20code%20facts%20and%20save.PNG)

