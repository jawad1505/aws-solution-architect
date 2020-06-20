
Table of Contents
### 1. RDS
### 2. Non RDS
### 3. Data Warehousing
### 4. ElastiCache
### 5. Lab
  ## 5.1. Create a RDS isntance
  ## 5.2. RDS Backups, Multi-AZ and Read Replicas
  
***************************

## 1.  RDS
* You cant ssh into RDS
* Max retention period 35 days
* RDS is not serverless, aurora serverless is serverless
* Backups:
  * Auto backups are enabled by default
  * back data is stored in S3
  * if RDS is of 20 GB back up will be of 20 GB
* Snapshots:
  * Are done manually
  * stored even after you delete the original RDS instance
  
 
> Whenever you retore a Restored backup or manual snapshot, the restored version will be a new RDS instance with new DNS end point
  
### RDS Two features

  1. Multi AZ - for Disaster Recovery  
     * Primary and secondary
     * failover is automatic
  
  2. Read Replicas - for performance 
      * Write on one DB1 is copied on DB2
      * For Read you can point your db
      * upto 5 read replicas of one DB
      * you can have read replicas in a second region
      * Backups should be ON for activating read replicas

### * Types of RDS Databases
  1. MYSQL
  2. MariaDB
  3. SQL Server
  4. Postgress
  5. Aurora
  6. Oracle
 

## 2. Non Relational Datbases
 * Dynamo DB
   * supports both document and key/value data
   * SSD Storage
   * Spread across 3 geographically distinct data centres
   * Evemtual Consistent Reads(Default)
      * Best Read Performance - consistency for all copies of data is usually reach within ***one second***
      * Repeating a read after short time 
   * Strongly Consistent Read
      * returns a result the reflects all writes that received a response prior to read (less than one second)
   
   Collection     = Table
   Document       = Row
   Key Value Pair = Fields
  
  * can have as many cols against a row
   
## 3. Data Warehousing
  * OLTP 
    * Online Transaction Processing: pulls up a row of such as Name, Date, Address etc
  
  * OLAP
    * Online Analytics Processing: Sum of Radios sold in Asia, USA, cost of radio in each region
      * Pulls large number of records
  
  * Redshift: Data warehousing solution or business intelligence
    * can scale to petabytes or more
    * only available in 1 AZ
    * less the 1/10th compared to other DWH solutions
    * Can be configured as
      * Single Node(160 GB)
      * Multi Node (leader/Computer Node)
    * Advanced Compression: compress individual columns
    * MPP: Massively Parallel Processing
    * Backups: Enabled by default, Max retention period 35 days
    * you are billed for 1 unit per node per hour
      * a 3 node DWS cluster running for a month would cost 2160 hours =(30 days * 24 hours * 3 Nodes)
      * will not be charged for leader node, only compute nodes will be charged
## 4. ElastiCache
  * webservice that makes it easy to deploy, operate and scale in memory cache in cloud
  * used to speed up performance of existing databases( frequent identical queries)
  * Supports 2 open-source in-memory caching engines:
     1. Redis
     2. Memcached
