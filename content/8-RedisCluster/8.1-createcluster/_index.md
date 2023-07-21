---
title : "Create Redis clusters"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 8.1. </b> "
---

1. Access to [Amazon ElastiCache service management console](https://console.aws.amazon.com/elasticache/home).
  + Open menu **Redis clusters**.
  + Click **Create Redis Cluster**.
![redis](/images/7.redis/001.png)

2. At the Redis cluster creation screen
  + In the **cluster creation method** section, select **Configure and create a new cluster**.
  + In the **Cluster mode** section, select **Disabled**.
  + In the **Name** field, enter **demo-cognito**.
  ![redis](/images/7.redis/002.png)
  + In the **Location** section, select **AWS Cloud**.
  + Uncheck the item **Multi-AZ** (because this is just a simple lab, no need for this feature).
  + Uncheck the item **Auto-failover** (because this is just a simple lab, no need for this feature).
    ![redis](/images/7.redis/003.png)
  + In the **Node type** section, select **t2.micro**.
  + In the **Number of replicas** field, enter **0**.
  + In the **Subnet groups** section, select **Create a new subnet group**.
  + In the **Name** field, enter **redis-cluster-subnet**.
  + In the **VPC ID** section, select **Demo-vpc**.
   ![redis](/images/7.redis/004.png)
  + In the **Manage subnets** section, tick 2 private subnets in the VPC demo, then click **Choose**.
  ![redis](/images/7.redis/005.png)
  + Click the **Next** button at the bottom of the page.
  + Go to the screen of **step 2: Advanced settings**, continue to scroll to the bottom of the page and then click **Next**.
  + Go to the screen of **step 3: Review and create**, check the information again, if there are no problems, then scroll to the bottom of the page and then click **Create**.
    ![redis](/images/7.redis/006.png)

3. At the detail screen of the Redis cluster
  + After creating the Redis cluster successfully, go to the detail screen and copy the **Primary endpoint** information.
  ![redis](/images/7.redis/007.png)
 