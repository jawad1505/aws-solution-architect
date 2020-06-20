# RDS Backups, Multi-AZ and Read Replicas

### Create MultiAZ
  * goto your RDS instance
  
  * Modify and set yes for multi AZ
  
  ![db](https://github.com/jawad1989/aws-solution-architect/blob/master/Databases/Labs/images/7%20-%20multiAZ.PNG)
  
  * Select Apply immediately and press save
  
### Create Read Replicas and manual backup
 * Modify RDS and select backups for any period of time i.e. 10
 * Save and wait for it
 * Goto actions-> Create Read Replica
 * Select new region (Optional)
 * Publicly accessible: No
 * Encryption: Disable
 * Give a name
 * Create Read Replica
