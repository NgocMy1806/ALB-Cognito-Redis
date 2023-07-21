---
title : "Register SSL certificate"
date :  "`r Sys.Date()`" 
weight : 2 
chapter : false
pre : " <b> 2.2 </b> "
---

1. Access the ACM service management interface
  + Click Request a certificate.
![ACM](/images/2.prerequisite/025-acm.png)

2. At the **Request certificate** screen
  + Click **Next**.
![ACM](/images/2.prerequisite/026-acm.png)

3. At the **Request public certificate** screen
  + In the **Fully qualified domain name** field, enter your domain.
  + In the **Add another name to this certificate**field, enter ***.domain**  to protect both your domain and your subdomains with this certificate.
  ![ACM](/images/2.prerequisite/027-acm.png)
  + Scroll down to the bottom of the page, and click  **Request**.

4. Click on **View certificate** that you just created
  + Click **Create records in Route 53**.
![ACM](/images/2.prerequisite/028-acm.png)
  + After the verification process is completed, AWS will automatically create a CNAME record for the SSL in the hosted zone.
  ![ACM](/images/2.prerequisite/029-acm.png)
  + Check to see if the status changes to **Issued**, indicating that you have successfully requested the certificate.
  ![ACM](/images/2.prerequisite/030-acm.png)