---
title : "Configure DNS record"
date :  "`r Sys.Date()`" 
weight : 6
chapter : false
pre : " <b> 6. </b> "
---


   In this step, we will configure route 53 so that when accessing the domain democognito.mymy.asia, the DNS server will point to EB's domain.
  + Access to [Route53 service management console](https://console.aws.amazon.com/route53/v2/home).
  + Click on **Hosted zones**.
  + Click on the name of the Hostes zone you created
![DNS](/images/6.dns/001.png)
  + Click **Create record**
  ![DNS](/images/6.dns/002.png)
  + In the **Record name** field, input **democognito**.
  {{% notice info %}}
  If you want to point the root domain directly to the EB environment, you can leave this field blank
  {{% /notice %}}
  + ON toggle **Alias**.
  + Select route traffic to **Alias to EB enviroment** in region **us-east-1**, then select created EB enviroment.
  + Click **Create records**
  ![DNS](/images/6.dns/003.png)

      After creating the record successfully, try to access it by pasting the **record name** of the newly created record into the browser.
      You should now see the browser display the application's index screen.
     ![DNS](/images/6.dns/004.png)
 
