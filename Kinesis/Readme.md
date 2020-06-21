 # Streaming Data
 Data generated contiuously by thousands of data sources, which typically send in the data records simultaneously, and in small sizes(KBs)
   * Purchases from online store - amazn
   * Stock Prices
   * GAme Data - gamer plays
   * Social Network Data - Twitter
   * GEospatial Data - uber
   * iOT sensor data
   
 # Kinesis
 Platform where you can send your streaming data to, Kinesis makes it easy to load and analyze streaming data and also provides the ability for you to buuld your own custom apps for your business needs.
 
 # Types of Kinesis
 
 ### 1. Kinesis Streams
    * Kinesis stream stores the data by data producers
      Examples Ec2, Mobile Phones using uber, laptop purchasing stocks, iOT farming data = data producers
    
    * Data Retention: 24 hours to 7 days
    
    * Data is stored in shards for
    
    * Consumers are EC2 that do the analysis e.g. EC2 analyze data from Kinesis Stream(such as data from twitter in shard) 
    
    * One analyzed, data can be sent to DynamoDB, S3, EMR, Redshift or RDS
    
    * Shards: 
        * 5 transactions per second for read; upto max of 2MB / second total read
        * upto 1000 records per second for writes, upto max of 1MB per second for writes
        * Data capacity of stream is a function of # of shards that you specify for the stream, total capacity of streams = sum of capacities of shards
      
 ### 2. Kinesis Firehose:
  * Stream data is sent to firehose, data is not stored. it has to do some operations using lambda.
  * outputs the data to S3/Elastic Search Cluster
  * No data persistence
  
### 3. Kinesis Analytics:
  * Works with Kinesis Streams, along with firehose, it analyzes the data on fly
  * then data is stored in S3, Redshift or Elastic Search CLuster
  
  
  
        
    
    
    
    
    
    
    
    
    
    
    
