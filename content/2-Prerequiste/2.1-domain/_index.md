---
title : "Register domain"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 2.1 </b> "
---
Route 53 is a scalable and highly available Domain Name System (DNS) service provided by AWS. It provides two main services: DNS and domain registration. To perform this lab, you need to prepare a domain that already has an SSL certificate. You can register a domain on Route 53 or register it from another domain provider like GoDaddy, Freenom, etc. and then transfer the DNS service to Route 53.

Because Route 53 is not the main content of this lab, I will briefly introduce the basic steps to transfer the DNS service from another domain provider to Route 53, without describing and explaining in detail.

Step 1: Register a domain with a domain provider like GoDaddy, Freenom, etc.

Step 2: Create a public hosted zone on Route 53. Name the hosted zone the same as the domain.

Step 3: After creating the hosted zone, you will have 4 NS records. Copy these 4 NS records, then access the Nameserver management screen in the domain provider and change the default NS records to the 4 NS records of the hosted zone on Route 53.

Step 4: Changing nameservers may take a few minutes to 24 hours. You can check if the NS record has been updated by opening a command prompt, then enter the command nslookup -q=ns {{domain}}
![DNS](/images/2.prerequisite/031-nslookup.png)

You can refer to the following video for how to do it: https://www.youtube.com/watch?v=L8YTHHweR3M&t=231s

After successfully updating the NS records, move on to the next step to register an SSL certificate for the domain.

