---
title : "Configure ALB"
date :  "`r Sys.Date()`" 
weight : 5
chapter : false
pre : " <b>5.</b> "
---

#### Configure rule for port 80
1. Access to [EC2 service management console](https://console.aws.amazon.com/ec2/v2/home).
  + Click **Load balancer**.
  + Click on the ALB just created by EB.
  + Open tab **Listener**.
  + Tick on listener **HTTP:80**, then click **Manage rules**.
![ALB](/images/3.alb/005-alb.png)

    At the manage rule screen for listener **HTTP:80**, we will proceed to set redirect all traffic from port 80 to 443 to ensure security.
  + Click icon **pen** to edit rule.
  + Click the **trash** icon to delete the current action, not allowing traffic to port 80 of the ALB to be forwarded directly to the target group.
![ALB](/images/3.alb/006-alb.png)
  + Click **Add action** to create new action, then click **Redirect to...**.
![ALB](/images/3.alb/007-alb.png)

  + In the **protocol** dropdown, select **HTTPS**.
  + In the **port** field, enter **443**.
  + Click the tick icon.
  + Click button **Update**.
![ALB](/images/3.alb/008-alb.png)

#### Configure rule for port 443
  Next, we will configure the rule for port 443 of ALB, so that when the user accesses the dashboard page, it will ask the user to log in with Amazon Cognito, if the user accesses the index page, it will forward directly to the target group.
  + First, go to the details screen of the newly created ALB.
  + Open tab **Listener**.
  + Tick the listener **HTTP:443**, then click **Manage rules**.

![ALB](/images/3.alb/009-alb.png)
  + Click icon **plus** then click **Insert rule**. 

![ALB](/images/3.alb/010-alb.png)
  + In the condition box, select **Path**, enter **/dashboard**, and then click the tick icon.
  + Click **Add Action**, then select **Authenticate**.
![ALB](/images/3.alb/011-alb.png)
  + In the **Cognito user pool** section, select the ID of the created user pool.
  + In the **App client** section, select the corresponding app of the user pool.
  + Click the tick icon.
![ALB](/images/3.alb/012-alb.png)
  + Click **Add action**, then click **Forward to...**.
![ALB](/images/3.alb/013-alb.png)
  + In the **target group** section, select the target group that has just been created by EB.
  + Click the tick icon.
  + Click button **Save**.
  ![ALB](/images/3.alb/014-alb.png)


      


