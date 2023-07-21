---
title : "Apply redis cho application"
date :  "`r Sys.Date()`" 
weight : 8
chapter : false
pre : " <b> 8.2. </b> "
---
#### Configure the .env file and install the predis package
+ Open source code extracted earlier with IDE such as Visual Studio Code, PHP Storm, ...
+ Edit the env related to session, redis as follows:
```
CACHE_DRIVER=redis
SESSION_DRIVER=redis
REDIS_HOST=primary endpoint of redis cluster
REDIS_CLIENT=predis
```
  ![redis](/images/7.redis/008.png)
+ Then, open terminal, run command `composer require predis/predis` to install predis package.
  {{% notice info %}}
  Predis is a PHP library used to work with Redis, a fast and powerful key-value cache in-memory database system. Predis provides an easy-to-use interface for connecting and interacting with Redis from your PHP application.
  {{% /notice %}}
![redis](/images/7.redis/009.png)
+ Compress the cognito-redis folder again.

#### Deploy new version 
+ Access the detail screen of the created EB enviroment.
+ Click **Upload and deploy**.
![redis](/images/7.redis/010.png)
+ In the **Upload and deploy** popup, upload the zipped cognito-redis folder.
+ In the **Version label** field, enter v1.1.
+ Click **Deploy**.
![redis](/images/7.redis/011.png)
