---
title : "Preparation "
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 2. </b> "
---

In this step, we will prepare some services to deploy the application.

{{% notice info %}}
To redirect the user to the requested page after successful login, we need to set up a callback URL with https on Cognito. Therefore, in addition to the basic resources in the VPC, you will need to prepare a public domain name and request an SSL certificate for that domain.
{{% /notice %}}

### Content
  1. [Register domain](2.1-domain/)
  2. [Request SSL certificate](2.2-ssl/)
  3. [Create VPC](2.3-vpc/)
  4. [Create Security group](2.4-sg/)
  5. [Create instance profile](2.5-ec2profile/)
