---
title : "ALB-Cognito-Redis"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
---
# Deploy a simple application that uses Amazon ElastiCache Redis for session storage, using a combination of ALB and Amazon Cognito for authentication

### Overall

 In this lab, you will practice creating a simple Laravel application that utilizes Amazon ElastiCache Redis to store sessions. Additionally, you will combine Application Load Balancer (ALB) and Amazon Cognito to implement authentication functionalities such as registration, login, and logout.

 Furthermore, during the lab, you will be introduced to how to transfer nameservers from a domain provider to Route 53, how to use AWS Certificate Manager to request an SSL certificate for the domain, and how to deploy applications quickly using Elastic Beanstalk.

 We hope this lab will be helpful for you on your "cloud journey" !


![ConnectPrivate](/images/arc-log.png) 

### Content

 1. [Introduce](1-introduce/)
 2. [Preparation](2-prerequiste/)
 3. [Configure Cognito](3-cognito/)
 4. [Deploy application](4-deploy/)
 5. [Configure ALB](5-configalb/)
 6. [Configure DNS](6-dns/)
 7. [Configure Redis cluster](7-rediscluster/)
 8. [Before applying Redis](8-beforeapplyredis/)
 9. [Test](9-test/)
 10. [Clean up resources](10-cleanup/)
