---
title : "Introduce"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 1. </b> "
---
In this lab, you will practice creating a simple Laravel application that uses Amazon ElastiCache Redis to store sessions, and combines Application Load Balancer (ALB) and Amazon Cognito for authentication functionalities (registration, login, logout).

This application is hosted on 2 EC2 instances behind ALB. When a user accesses a public page (accessible to anyone), ALB will directly route the request to one of the EC2 instances. If a user accesses a private page (only accessible to logged-in users), ALB will route the request to Cognito. After the user completes the login process on Cognito, ALB will direct the user to the requested resource on EC2.

With such a 2 EC2 structure, to ensure session continuity and consistency across all instances, this application will use Amazon ElastiCache Redis instead of saving the session right on the file driver of each server.

Additionally, this lab will guide you on how to deploy the system quickly, flexibly, and with high availability using the Elastic Beanstalk service.

#### Application Load Balancer (ALB)
ALB is a service provided by Amazon Web Services (AWS) that offers load balancing and traffic routing solutions for applications running on multiple servers.

#### Amazon Cognito
Amazon Cognito is a login and authentication management service for web and mobile applications. It enables developers to authenticate and authorize users through social Identity Providers (IdP) such as Facebook, Google, and Amazon, or through custom user accounts. Cognito provides user management, authorization, and activity tracking features, helping to reduce development effort and improve security for applications.

#### Amazon ElastiCache Redis
Amazon ElastiCache is a fully managed, compatible Redis and Memcached service that provides cost-optimized, real-time performance for modern applications. ElastiCache scales to handle hundreds of millions of operations per second with microsecond response times, while ensuring enterprise-grade security and reliability.

Amazon ElastiCache for Redis is an excellent choice for deploying a highly available, distributed, and secure in-memory cache to reduce access latency, increase throughput, and offload your relational or NoSQL databases and applications.

#### AWS Elastic Beanstalk 
Elastic Beanstalk provides a simple platform for deploying web applications without requiring deep knowledge of infrastructure. By using Elastic Beanstalk, you can focus on developing your application without worrying about configuring and managing underlying infrastructure resources such as servers, networks, and databases.

  {{% notice info %}}
  This lab is an extension of the lab "Deploying a simple website with authentication function using ALB and Amazon Cognito"

  Additional features included: Backend logout handling (clearing ALB cookies); Decoding ALB headers to display user information fetched from Cognito; Storing sessions on Redis Cluster.
  You can access the source code to see the detailed implementation.
  {{% /notice %}}

![Architecture](/images/arc-log.png) 