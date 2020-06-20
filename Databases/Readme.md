
Table of Contents
### 1. RDS
### 2. Non RDS
### 3. Data Warehousing
### 4. ElastiCache
### 5. Lab
  ## 5.1. Create a RDS isntance
  
***************************

## 1.  RDS
* You cant ssh into RDS
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

### * Types of RDS Databases
  1. MYSQL
  2. MariaDB
  3. SQL Server
  4. Postgress
  5. Aurora
  6. Oracle
 

## 2. Non Relational Datbases
    
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
  
## 4. ElastiCache
  * webservice that makes it easy to deploy, operate and scale in memory cache in cloud
  * used to speed up performance of existing databases( frequent identical queries)
  * Supports 2 open-source in-memory caching engines:
     1. Redis
     2. Memcached
