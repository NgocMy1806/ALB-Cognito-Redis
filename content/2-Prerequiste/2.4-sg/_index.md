---
title : "Create security groups"
date : "`r Sys.Date()`"
weight : 4
chapter : false
pre : " <b> 2.4 </b> "
---

#### Create security groups

In this step, we will proceed to create the security groups used for ALB, instance và ElastiCache Redis cluster. 

#### Create security group for ALB

1. Go to [VPC service management console](https://console.aws.amazon.com/vpc)
  + Click **Security Group**.
  + Click **Create security group**.

![SG](/images/2.prerequisite/019-createsg.png)

2. At the **Create security group** screen
  + **Security group name**, enter **SG ALB**. 
  + **Description**, enter **SG ALB**.
  + **VPC**, click **X** icon to select the **Demo-vpc** you created for this lab.

![SG](/images/2.prerequisite/007-createsgalb.png)
  + Create 2 inbound rules that allow receive traffic to port 80 and 443 from the internet as below.
![SG](/images/2.prerequisite/008-createsgalb1.png)

  + Check  **Outbound rule**, then click **Create security group**.


#### Create a security group for Linux instance in public subnet

1. Go to [VPC service management console](https://console.aws.amazon.com/vpc)
  + Click **Security Group**.
  + Click **Create security group**.

![SG](/images/2.prerequisite/019-createsg.png)

2. At the **Create security group** screen
  + **Security group name**, enter **SG Public Linux Instance**. 
  + **Description**, enter **SG Public Linux Instance**.
  + **VPC**, click **X** icon to select the **Demo-vpc** you created for this lab.
![SG](/images/2.prerequisite/009-createec2sg.png)

  + The EC2 instance does not receive traffic directly from users but through the ALB, so we will configure the inbound rule to allow traffic only through the HTTP protocol, port 80 from the source Security group of the ALB.
  + Next, to be able to SSH into the instance, we need to create an inbound rule for port 22 from **My IP**.
  ![SG](/images/2.prerequisite/010-createec2sg1.png)

  + Check  **Outbound rule**, then click **Create security group**.

#### Create a security group for ElastiCache Redis cluster

1. Go to [VPC service management console](https://console.aws.amazon.com/vpc)
  + Click **Security Group**.
  + Click **Create security group**.

![SG](/images/2.prerequisite/019-createsg.png)

2. At the **Create security group** screen
  + **Security group name**, enter **SG Redis**. 
  + **Description**, enter **SG Redis**.
  + **VPC**, click **X** icon to select the **Demo-vpc** you created for this lab.
![SG](/images/2.prerequisite/011-createredissg.png)

  + To enable communication with EC2, we need to open an inbound rule for port 6379 with the source is EC2's Security Group.

![SG](/images/2.prerequisite/012-createredissg.png)

  + + Check  **Outbound rule**, then click **Create security group**.

#### Adding an inbound rule for the security group of Linux instance: 

  In order for EC2 to communicate with the Redis cluster, we need to perform the following steps:
   + From the **Security groups** screen, select **SG Pulic Linux Instance**.
   + Select the **Inbound rules** tab, then click **Edit inbound rules**.
    ![SG](/images/2.prerequisite/011-createec2sg.png)
  + At the **Edit inbound rules** screen, open an inbound rule for port 6379, with source is the Security group of the Redis cluster.
    ![SG](/images/2.prerequisite/012-createec2sg.png)
    
    So, we have completed creating all the necessary security groups for the EC2 instance, ALB, and ElastiCache Redis cluster.