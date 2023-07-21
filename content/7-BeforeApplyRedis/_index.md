---
title : "Before applying Redis"
date :  "`r Sys.Date()`" 
weight : 7 
chapter : false
pre : " <b> 7. </b> "
---
- Type the address **https://subdomain/demo-cognito/** into the browser

     (Substitute your respective subdomain for “subdomain” in the URL)

- Click **Go to my page**
 ![DNS](/images/6.dns/004.png)

- You will now be navigated to Cognito's Sign in screen. If you do not have an account, please click on the text link **Sign up**, register, then login.
![test](/images/5.test/002-login.png)
- Once logged in, you will be redirected to the correct dashboard screen.
Pay attention to the **EC2 ID** information and the number of times **visit page**.
- Do F5 continuously, you will see that if you are in EC2-1, next time F5, if you are still navigated into EC2-1, the number of **visit page** will increase by 1 unit. However, if the next F5 you are redirected to EC2-2, the **visit page** will be recounted from 1.
![test](/images/5.test/1.png)
![test](/images/5.test/2.png)
- The reason is because by default, our application will store session and the cache in **file driver**, which means it will be saved directly on the server. Therefore, the sessions on the 2 EC2s are completely unrelated, so when we are redirected to EC2-2, the system will start a new session, not update the existing session.

     To solve this problem, we will use AWS's Amazon ElastiCache Redis to store the session of the servers in the same redis cluster.


