* in this lab we will create a new read replica of mysql to aurora
  * it will take backup of mysql
  * migrate mysql database to aurora
  
* select your MYSQL RDS instance
* goto action-> create aurora read replica
* DB identifer: jawadAurora


 ![readR](https://github.com/jawad1989/aws-solution-architect/blob/master/Databases/Labs/images/11%20-%20Create%20rEad%20Replica.PNG)
 
 
 ![rR](https://github.com/jawad1989/aws-solution-architect/blob/master/Databases/Labs/images/12%20-%20Aurora%20Read%20Replica.PNG)

## Promote Aurora MYSQL - Migration
 * Select cluster node goto action->promote 
 
 ![Promote](https://github.com/jawad1989/aws-solution-architect/blob/master/Databases/Labs/images/13%20-%20Promote%20Read%20Replica.PNG)
 
 * this will promote mysql database to standalone aurora database
  
 We can also take snapshot of aurora db and restore a new aurora from that snapshot
 
 
