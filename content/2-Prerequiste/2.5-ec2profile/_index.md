---
title : "Create instance profile"
date :  "`r Sys.Date()`" 
weight : 5
chapter : false
pre : " <b> 2.5</b> "
---

1. Go to [IAM service management console](https://console.aws.amazon.com/iamv2/home) to create instance role
  + Click **Roles**.
  + Click **Create role**.
  
![role](/images/2.prerequisite/ec2profile/001.png)

2. At the **Create role** screen
  + In **Trusted entity type**, choose **AWS service** 
  + In **Use case**, choose **EC2**.

![role](/images/2.prerequisite/ec2profile/002.png)

  + Select policy **AmazonElastiCacheFullAccess**.
![role](/images/2.prerequisite/ec2profile/003.png)  
  + Select policy **AWSElasticBeanstalkWebTier**.
![role](/images/2.prerequisite/ec2profile/003-1.png)  
  + Click **Next**.

  + In **Role name** field, enter **Redis_role**.
  + Scroll to the bottom of the screen, click **Create role**.

![role](/images/2.prerequisite/ec2profile/004.png)  

