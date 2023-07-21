---
title : "Test"
date :  "`r Sys.Date()`" 
weight : 9
chapter : false
pre : " <b> 9. </b> "
---
- Type the address **https://subdomain/demo-cognito/** into the browser

     (Substitute your respective subdomain for “subdomain” in the URL)

- Click on **Go to my page** and then login.
![DNS](/images/6.dns/004.png)
 
- Proceed to F5 continuously.
https://drive.google.com/file/d/13F1_owuio3eYqvFjUXHnmzpdzqd4m02a/view?usp=sharing
- You can see that, even though we alternately navigate between 2 EC2, but every time F5, visit time is incremented by 1, indicating that we have deployed redis successfully.

   Congratulations, you have just completed the lab. Remember to perform resource cleanup to avoid unintended costs.