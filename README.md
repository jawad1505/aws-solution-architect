# [aws-solution-architect](https://aws.amazon.com/certification/certification-prep/)

# Table of Contents

## IAM & S3
  * [IAM LAB](https://github.com/jawad1989/aws-solution-architect/tree/master/IAM%26S3)
  * [Create a Blling Alarm](https://github.com/jawad1989/aws-solution-architect/blob/master/IAM%26S3/Create-Billing-Alaram.md)
  * [Create a S3 Bucket](https://github.com/jawad1989/aws-solution-architect/blob/master/IAM&S3/Create-S3-Bucket.md)
  * [S3 Pricing Tiers](https://github.com/jawad1989/aws-solution-architect/blob/master/IAM&S3/S3-Pricing-Tiers.md)
  * [S3 Security & Encryption](https://github.com/jawad1989/aws-solution-architect/blob/master/IAM%26S3/S3-Security.md)
  * [S3 Versioning](https://github.com/jawad1989/aws-solution-architect/blob/master/IAM%26S3/S3-Versioning.md)
  * [S3 LifeCycle](https://github.com/jawad1989/aws-solution-architect/blob/master/IAM%26S3/S3-Lifecycle.md)
  * Cloud Front
  * Transfer Acceleration
  * Snow Ball
  * S3
  * IAM 
  * Storage Gateway
     * File Gateway(NFS & SMP):  flat files stored directly in S3
     * Volume Gateway(iSCSI): way of storing copying your hard dsk drives or virtual hard disk drives in S3
       * Stored Volume: lets you store primary data locally while asynchronously backing up data to aWS in form of EBS
       * Cached Volume: Entire Dataset is stored on S3 and most frequently access data is cached on site
     * Tape Gateway (VTL) Virtual Tape Library
  * Athena VS Macie
    * Interactive query service which enables you to analyse and query data located in S3 using standard SQL
       * you pay per query, serverless
  * PII( Personally Identifiable Information): personal data used to establish an individual's identity e.g. SSN, back account number
  * Macie: Security Service that used MachineLearning and Natural Language Processing to discover, classify and protect data stored in S3. Checks your S3 Objects to recongnize that if your S3 contains data such as PII  
   
