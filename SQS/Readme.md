Amazon Simple Queue Service (SQS) is a fully managed message queuing service that enables you to decouple and scale microservices, distributed systems, and serverless applications. 

SQS eliminates the complexity and overhead associated with managing and operating message oriented middleware, and empowers developers to focus on differentiating wor

SQS offers two types of message queues.
1. ***Standard queues*** offer maximum throughput, best-effort ordering, and at-least-once delivery. ***nearly unlimited TPS***
2. ***SQS FIFO queues*** are designed to guarantee that messages are processed exactly once, in the exact order that they are sent. ***300 TPS ***

Long Polling:
way to retreive message from SQS, no response until a message arrivs or long poll times off

Short polling:
returns immediately even if queue is empty



Examples of SQS:
* Meme update using SQS
* Travael Website: SkyScanner 
* ***DECOUPLE***

* Oldest service in AWS
* Message can contain upto 256 KB(can be go above will be saved in s3) of text in any format
* pull based,  not push
* Retention upto 14 days, default 4 days
* Visibility Time: amount of time the message is invisble in SQS after reader picks ip up, if job is processed within this time message will be deleted, if not message will become visible again. (SAME message being delivered Twice) ***MAX Visibility Time 12 hours***  
